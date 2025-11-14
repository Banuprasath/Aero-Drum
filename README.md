# 🥁 Aero Drum Project – Setup & Run Guide  
**MPU6050 + Arduino Uno + Python**

## 📦 Requirements
- Arduino Uno  
- Two MPU6050 sensors  
- Jumper wires  
- USB cable  
- Arduino IDE  
- Python (with `pyserial`, `pygame`, or similar modules)  
- PC with audio support  

---

## 🔌 MPU6050 Wiring

To connect two MPU6050 sensors on the same I2C bus:

### MPU 1:
- `VCC`  → 5V  
- `GND`  → GND  
- `SDA`  → A4  
- `SCL`  → A5  
- `AD0`  → GND *(I2C address: `0x68`)*

### MPU 2:
- `VCC`  → 5V  
- `GND`  → GND  
- `SDA`  → A4  
- `SCL`  → A5  
- `AD0`  → 5V *(I2C address: `0x69`)*

> 💡 *Both sensors share the same I2C bus but have different addresses due to AD0 pin settings.*

---

## 🚀 Running Steps

1. **Connect both MPU6050 sensors** to Arduino as shown above.  
2. **Open Arduino IDE**.  
3. **Install required libraries**:  
   - `Wire.h`  
   - `I2Cdevlib`  
   - `MPU6050` library  

4. **Upload the Arduino sketch** (`aerodrum.ino`) to the board.

> ⚠️ After uploading, **close the Arduino Serial Monitor**!  
> Only **one program** can use the serial port at a time.  
> Keeping Serial Monitor open will **prevent Python from reading data**.

5. **Run your Python script** (`aerodrum.py`) to read serial data and play drum sounds.  
6. **Swing your hands** to simulate drum hits. Python will detect motion and trigger sounds.

---

## 🛠️ Tips
- Calibrate sensors to reduce noise and drift.  
- Adjust motion detection thresholds in the code.  
- Assign separate drum sounds to each hand (sensor).  

---

## 🧰 Troubleshooting

- **Serial Errors in Python**:  
  - Ensure Arduino Serial Monitor is **closed**.  
  - Double-check the **COM port** used in your script.

- **No Sound Output**:  
  - Verify that **PC audio is enabled**.  
  - Check if `pygame` or sound module is functioning.

- **Lag or Inaccurate Response**:  
  - Try running the Python script with **admin/terminal privileges**.

---

## 🎉 Enjoy Air Drumming!

Crafted with passion by **Banu Prasath, Siva Shunmugam, Pravin, KarthiKeyan**
