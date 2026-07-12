# IoT Trail Intelligence System

A bike-mounted embedded system that passively collects and analyzes 
trail condition data across rides in real time.

## What it does
A Raspberry Pi Zero 2W device mounted to a bike logs GPS-tagged 
accelerometer, temperature, humidity, and timestamp data locally 
during rides. On returning to WiFi, the device automatically syncs 
ride data to a cloud database. An onboard OLED display and buzzer 
provide real-time anomaly alerts when terrain roughness deviates 
significantly from historical baseline data for a given trail segment.

A Next.js web dashboard renders colour-coded GPS trail maps using 
Leaflet.js, and the Claude API generates natural language post-ride 
analysis — terrain breakdowns, condition changes, and next-ride 
predictions.

## Stack
**Hardware:** Raspberry Pi Zero 2W · MPU-6050 · Neo-6M GPS · 
DHT22 · DS3231 RTC · SH1106 OLED · Passive Buzzer

**Device software:** Python 3 · gpsd · pynmea2 · smbus2 · 
adafruit-circuitpython-dht

**Backend:** Supabase (Postgres + REST API)

**Frontend:** Next.js 14 · Tailwind CSS · Leaflet.js · Vercel

**AI:** Claude API (claude-sonnet-4-6) — post-ride analysis pipeline

## Architecture
Sensor collection → local SD card logging → WiFi auto-sync → 
Supabase → Claude API inference → Next.js dashboard

## Wiring Schematic

![Wiring Schematic](SchematicIoT.png)
