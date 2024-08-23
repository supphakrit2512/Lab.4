# Lab.4

import RPi.GPIO as GPIO
import time

RED_PIN = 12
GREEN_PIN = 16
BLUE_PIN = 18

GPIO.setmode(GPIO.BOARD)
GPIO.setup(RED_PIN, GPIO.OUT)
GPIO.setup(GREEN_PIN, GPIO.OUT)
GPIO.setup(BLUE_PIN, GPIO.OUT)

def set_color(red, green, blue):
    GPIO.output(RED_PIN, red)
    GPIO.output(GREEN_PIN, green)
    GPIO.output(BLUE_PIN, blue)

try:
    while True:
        set_color(True, False, False)
        time.sleep(1)

        set_color(False, True, False)
        time.sleep(1)

        set_color(False, False, True)
        time.sleep(1)

        set_color(True, True, False)
        time.sleep(1)

        set_color(True, False, True)
        time.sleep(1)

        set_color(False, True, True)
        time.sleep(1)

        set_color(True, True, True)
        time.sleep(1)

        set_color(False, False, False)
        time.sleep(1)

except KeyboardInterrupt:
    pass

finally:
    GPIO.cleanup()
    print("\nBye....")

