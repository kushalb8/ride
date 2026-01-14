package com.example.miniridebooking

import android.content.Intent
import android.os.Bundle
import android.os.Handler
import android.os.Looper
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class BookRideActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_book_ride)

        val btnBook = findViewById<Button>(R.id.btnBook)
        val tvStatus = findViewById<TextView>(R.id.tvStatus)
        val btnSafety = findViewById<Button>(R.id.btnSafety)

        btnBook.setOnClickListener {
            tvStatus.text = "Searching for Ride..."

            Handler(Looper.getMainLooper()).postDelayed({
                tvStatus.text = "Ride Assigned"
            }, 5000)
        }

        btnSafety.setOnClickListener {
            startActivity(Intent(this, SafetyActivity::class.java))
        }
    }
}
