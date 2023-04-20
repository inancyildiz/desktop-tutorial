
import RPi.GPIO as GPIO
from tkinter import *

# Motorlar için kullanılacak pinleri tanımlayalım
# sol motorun kontrolü için
in1 = 23
in2 = 24
en1 = 25
# sağ motorun kontrolü için
in3 = 17
in4 = 27
en2 = 22

# GPIO modunu belirleyelim
GPIO.setmode(GPIO.BCM)

# Pinleri çıkış olarak ayarlayalım
GPIO.setup(in1,GPIO.OUT)
GPIO.setup(in2,GPIO.OUT)
GPIO.setup(en1,GPIO.OUT)
GPIO.setup(in3,GPIO.OUT)
GPIO.setup(in4,GPIO.OUT)
GPIO.setup(en2,GPIO.OUT)

# PWM nesnelerini oluşturalım
pwm1 = GPIO.PWM(en1, 100)
pwm2 = GPIO.PWM(en2, 100)

# PWM sinyallerini başlatalım
pwm1.start(0)
pwm2.start(0)

# Sol motoru ileri hareket ettirelim
def forward_left(speed):
    GPIO.output(in1,GPIO.HIGH)
    GPIO.output(in2,GPIO.LOW)
    pwm1.ChangeDutyCycle(speed)

# Sol motoru geri hareket ettirelim
def reverse_left(speed):
    GPIO.output(in1,GPIO.LOW)
    GPIO.output(in2,GPIO.HIGH)
    pwm1.ChangeDutyCycle(speed)

# Sağ motoru ileri hareket ettirelim
def forward_right(speed):
    GPIO.output(in3,GPIO.HIGH)
    GPIO.output(in4,GPIO.LOW)
    pwm2.ChangeDutyCycle(speed)

# Sağ motoru geri hareket ettirelim
def reverse_right(speed):
    GPIO.output(in3,GPIO.LOW)
    GPIO.output(in4,GPIO.HIGH)
    pwm2.ChangeDutyCycle(speed)

# GUI penceresini oluşturalım
window = Tk()
window.title("Motor Kontrol Paneli")

# Sol motor hızı için kaydırıcı oluşturalım
left_speed_slider = Scale(window, from_=0, to=100, orient=HORIZONTAL, label="Sol Motor Hızı", length=200, command=forward_left)
left_speed_slider.pack()

# Sağ motor hızı için kaydırıcı oluşturalım
right_speed_slider = Scale(window, from_=0, to=100, orient=HORIZONTAL, label="Sağ Motor Hızı", length=200, command=forward_right)
right_speed_slider.pack()

# GUI'yi çalıştıralım
window.mainloop()

