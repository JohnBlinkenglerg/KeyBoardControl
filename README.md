from djtellopy import tello
import KeyPressModule as kp
from time import sleep

kp.init()
tello = tello.Tello()
tello.connect
print(tello.get_battery())

def getKeyboardInput
    lr, rb, ud, yv = 0, 0, 0, 0
    speed = 50

    if kp.getKey("LEFT"): lr = -speed
    elif kp.getKey("RIGHT"): lr = speed

    if kp.getKey("UP"): fb = speed
    elif kp.getKey("DOWN"): fb = -speed

    if kp.getKey("w"): fb = speed
    elif kp.getKey("s"): fb = -speed

    if kp.getKey("a"): yv = speed
    elif kp.getKey("d"): yv = -speed

    if kp.getKey("q"): tello.land


    return [lr, rb, ud, yv]


tello.takeoff()

while True:
    vals = getKeyboardInput()
    tello.send_rc_control(vals[0], vals[1], vals[2], vals[3])
    sleep(0.05)
