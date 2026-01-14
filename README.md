package com.example.miniridebooking

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val pickup = findViewById<EditText>(R.id.etPickup)
        val drop = findViewById<EditText>(R.id.etDrop)
        val btnCalculate = findViewById<Button>(R.id.btnCalculate)
        val tvDistance = findViewById<TextView>(R.id.tvDistance)
        val tvFare = findViewById<TextView>(R.id.tvFare)
        val btnBookRide = findViewById<Button>(R.id.btnBookRide)

        btnBookRide.isEnabled = false

        btnCalculate.setOnClickListener {
            if (pickup.text.isEmpty() || drop.text.isEmpty()) {
                Toast.makeText(this, "Please enter pickup and drop", Toast.LENGTH_SHORT).show()
                return@setOnClickListener
            }

            val distance = 10 // mocked distance
            val fare = 10 + (distance * 12)

            tvDistance.text = "Distance: $distance km"
            tvFare.text = "Fare: ₹$fare"

            btnBookRide.isEnabled = true
        }

        btnBookRide.setOnClickListener {
            startActivity(Intent(this, BookRideActivity::class.java))
        }
    }
}
