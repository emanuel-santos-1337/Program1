ConexaoIgreja/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── suaigreja/
│   │   │   │           ├── MainActivity.java
│   │   │   │           ├── ChatActivity.java
│   │   │   │           ├── CalendarActivity.java
│   │   │   │           ├── TaskManagerActivity.java
│   │   │   │           └── FeedbackActivity.java
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   │   ├── activity_main.xml
│   │   │   │   │   ├── activity_chat.xml
│   │   │   │   │   ├── activity_calendar.xml
│   │   │   │   │   ├── activity_task_manager.xml
│   │   │   │   │   └── activity_feedback.xml
│   │   │   │   └── values/
│   │   │   │       ├── strings.xml
│   │   │   │       └── colors.xml
│   │   │   └── AndroidManifest.xml
│   │   └── build.gradle
│   └── build.gradle
│
├── .gitignore
├── README.md
└── build.gradle

package com.suaigreja;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button chatButton = findViewById(R.id.chatButton);
        Button calendarButton = findViewById(R.id.calendarButton);
        Button taskManagerButton = findViewById(R.id.taskManagerButton);
        Button feedbackButton = findViewById(R.id.feedbackButton);

        chatButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, ChatActivity.class));
            }
        });

        calendarButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, CalendarActivity.class));
            }
        });

        taskManagerButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, TaskManagerActivity.class));
            }
        });

        feedbackButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, FeedbackActivity.class));
            }
        });
    }
}
dependencies {
    implementation 'androidx.appcompat:appcompat:1.3.1'
    implementation 'com.google.android.material:material:1.4.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.0'
}
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.suaigreja">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.AppCompat.Light.NoActionBar">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".ChatActivity" />
        <activity android:name=".CalendarActivity" />
        <activity android:name=".TaskManagerActivity" />
        <activity android:name=".FeedbackActivity" />
    </application>

</manifest>

package com.suaigreja;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button chatButton = findViewById(R.id.chatButton);
        Button calendarButton = findViewById(R.id.calendarButton);
        Button taskManagerButton = findViewById(R.id.taskManagerButton);
        Button feedbackButton = findViewById(R.id.feedbackButton);

        chatButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, ChatActivity.class));
            }
        });

        calendarButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, CalendarActivity.class));
            }
        });

        taskManagerButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, TaskManagerActivity.class));
            }
        });

        feedbackButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(MainActivity.this, FeedbackActivity.class));
            }
        });
    }
}

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/chatButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Chat"
        app:layout_constraintBottom_toTopOf="@+id/calendarButton"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:layout_margin="16dp"/>

    <Button
        android:id="@+id/calendarButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text

        <?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/titleTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Conexão Igreja"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_marginTop="32dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/chatButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Chat"
        app:layout_constraintTop_toBottomOf="@+id/titleTextView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_margin="16dp"/>

    <Button
        android:id="@+id/calendarButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Calendário"
        app:layout_constraintTop_toBottomOf="@+id/chatButton"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_margin="16dp"/>

    <Button
        android:id="@+id/taskManagerButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Gerenciar Tarefas"
        app:layout_constraintTop_toBottomOf="@+id/calendarButton"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_margin="16dp"/>

    <Button
        android:id="@+id/feedbackButton"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Feedback"
        app:layout_constraintTop_toBottomOf="@+id/taskManagerButton"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_margin="16dp"/>

</androidx.constraintlayout.widget.ConstraintLayout>
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Chat"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        android:layout_margin="16dp"/>

    <!-- Aqui você pode adicionar uma lista de mensagens, campo de entrada, etc. -->

</androidx.constraintlayout.widget.ConstraintLayout>

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Calendário"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"

       


        


