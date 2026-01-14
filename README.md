package com.example.miniridebooking

import android.os.Bundle
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class SafetyActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_safety)

        val btnSOS = findViewById<Button>(R.id.btnSOS)
        val tvSOS = findViewById<TextView>(R.id.tvSOS)

        btnSOS.setOnClickListener {
            val latitude = 17.3850
            val longitude = 78.4867

            tvSOS.text =
                "Emergency alert sent with your live location\nLat: $latitude, Lng: $longitude"
        }
    }
}
