class LoginActivity : AppCompatActivity() {
    private lateinit var auth: FirebaseAuth

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_login)

        auth = FirebaseAuth.getInstance()

        val btnLogin = findViewById<Button>(R.id.btnLogin)
        val email = findViewById<EditText>(R.id.email)
        val senha = findViewById<EditText>(R.id.senha)

        btnLogin.setOnClickListener {
            auth.signInWithEmailAndPassword(email.text.toString(), senha.text.toString())
                .addOnCompleteListener { task ->
                    if (task.isSuccessful) {
                        startActivity(Intent(this, MainActivity::class.java))
                    } else {
                        Toast.makeText(this, "Falha no login!", Toast.LENGTH_SHORT).show()
                    }
                }
        }
    }
}


class ChatActivity : AppCompatActivity() {
    private lateinit var database: DatabaseReference

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_chat)

        database = FirebaseDatabase.getInstance().getReference("mensagens")

        val btnEnviar = findViewById<Button>(R.id.btnEnviar)
        val campoMensagem = findViewById<EditText>(R.id.campoMensagem)

        btnEnviar.setOnClickListener {
            val mensagem = campoMensagem.text.toString()
            val novaMensagem = Mensagem("Emanuel", mensagem)

            database.push().setValue(novaMensagem)
        }
    }
}

data class Mensagem(val usuario: String, val texto: String)

class EventoService : FirebaseMessagingService() {
    override fun onMessageReceived(remoteMessage: RemoteMessage) {
        remoteMessage.notification?.let {
            enviarNotificacao(it.title ?: "Novo Evento", it.body ?: "Detalhes do evento.")
        }
    }

    private fun enviarNotificacao(titulo: String, mensagem: String) {
        val builder = NotificationCompat.Builder(this, "canal_eventos")
            .setSmallIcon(R.drawable.ic_evento)
            .setContentTitle(titulo)
            .setContentText(mensagem)
            .setPriority(NotificationCompat.PRIORITY_HIGH)

        val manager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
        manager.notify(0, builder.build())
    }
}
