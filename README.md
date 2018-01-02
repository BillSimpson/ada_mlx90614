# ada_mlx90614
Driver for IR thermometer MLX90614 based upon Adafruit CircuitPython (for micro controllers)

This is an i2c driver for the Melexis MLX90614 family of infrared
thermometers.  The driver was developed using Adafruit Circuitpython.
It has been used with a Adafruit Feather Huzzah ESP8266 microcontroller.
Note that my board uses "bitbangio" for the i2c communications.  If your
microcontroller supports hardware i2c, then substitute "busio" for "bitbangio".

#### Requirements:

The driver was developed using Circuitpython 2.2.0

This driver uses the "adafruit_bus_device.i2c_device" driver.

#### Example:

```
import board
import bitbangio   # use busio if supported
import ada_mlx90614
i2c = bitbangio.I2C(board.SCL, board.SDA)  # substitute busio if supported
irsensor = ada_mlx90614.MLX90614(i2c)
print(irsensor.temp_amb_c)
print(irsensor.temp_obj_c)
if irsensor.dualzone:
    print(irsensor.temp_obj2_c)
```

