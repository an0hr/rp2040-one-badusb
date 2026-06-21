# rp2040-one-badusb
hi i made a badusb for the board rp2040-one.
it is hella easy 
1. step flash your board with the 2UF file given
2. or the link no problem:
3. flash it with circuitpy
4. then add the lib file i give
5. or the link bellow
6. name the your script "code.py"
7. and it gets exocuted
8. imma give the file about anything and imma help for the libary codes

btw that how you program it in turkish and english
and the keyboard it only supports US style
i culdnt find turkish one

=======================================================
  RP2040 CircuitPython HID - Komut Referans Kilavuzu
  RP2040 CircuitPython HID - Command Reference Guide
=======================================================
 
-------------------------------------------------------
1. KUTUPHANELER / LIBRARIES
-------------------------------------------------------
 
import usb_hid
  TR: RP2040'i USB cihaz olarak kullanmak icin ana kutüphane.
  EN: Main library to use RP2040 as a USB device.
 
from adafruit_hid.keyboard import Keyboard
  TR: Klavye islevlerini saglar.
  EN: Provides keyboard functions.
 
from adafruit_hid.keyboard_layout_us import KeyboardLayoutUS
  TR: Harf ve metin yazmak icin ABD klavye duzeni.
  EN: US keyboard layout for typing letters and text.
 
from adafruit_hid.keycode import Keycode
  TR: ALT, ENTER, F4 gibi ozel tus kodlari buradan gelir.
  EN: Special key codes like ALT, ENTER, F4 come from here.
 
import time
  TR: Bekleme islemi icin.
  EN: For wait operations.
 
-------------------------------------------------------
2. DEGISKENLER / VARIABLES
-------------------------------------------------------
 
kbd = Keyboard(usb_hid.devices)
  TR: Klavyeyi baslatir. 'kbd' yerine istedigin ismi yazabilirsin.
  EN: Initializes the keyboard. You can use any name instead of 'kbd'.
 
layout = KeyboardLayoutUS(kbd)
  TR: Harf yazmak icin kullanilan arac.
  EN: Tool used for typing letters.
 
-------------------------------------------------------
3. TEMEL KOMUTLAR / BASIC COMMANDS
-------------------------------------------------------
 
kbd.press(Keycode.X)
  TR: Tusa basar ve basili tutar.
  EN: Presses and holds the key.
 
kbd.release_all()
  TR: Basili tum tuslari birakir. BUNU UNUTMA!
  EN: Releases all held keys. DON'T FORGET THIS!
 
kbd.release(Keycode.X)
  TR: Sadece o tusu birakir.
  EN: Releases only that specific key.
 
layout.write("metin")
  TR: Metni klavyeden yazar.
  EN: Types text via keyboard.
 
layout.write("metin\n")
  TR: Metin yazar ve Enter'a basar. \n = Enter demek.
  EN: Types text and presses Enter. \n = Enter.
 
time.sleep(0.1)   --> 100 milisaniye / milliseconds
time.sleep(0.01)  --> 10 milisaniye / milliseconds
time.sleep(1)     --> 1 saniye / second
 
-------------------------------------------------------
4. DONGU / LOOP
-------------------------------------------------------
 
for i in range(15):
    kbd.press(Keycode.ALT, Keycode.F4)
    kbd.release_all()
    time.sleep(0.01)
 
  TR: range(15) = 15 kere tekrarla. i = kacinci tekrar (0'dan baslar).
  EN: range(15) = repeat 15 times. i = which repetition (starts from 0).
 
-------------------------------------------------------
5. HARF TUSLARI / LETTER KEYS
-------------------------------------------------------
 
Keycode.A    Keycode.B    Keycode.C    Keycode.D
Keycode.E    Keycode.F    Keycode.G    Keycode.H
Keycode.I    Keycode.J    Keycode.K    Keycode.L
Keycode.M    Keycode.N    Keycode.O    Keycode.P
Keycode.Q    Keycode.R    Keycode.S    Keycode.T
Keycode.U    Keycode.V    Keycode.W    Keycode.X
Keycode.Y    Keycode.Z
 
-------------------------------------------------------
6. SAYI TUSLARI / NUMBER KEYS
-------------------------------------------------------
 
Keycode.ZERO     --> 0
Keycode.ONE      --> 1
Keycode.TWO      --> 2
Keycode.THREE    --> 3
Keycode.FOUR     --> 4
Keycode.FIVE     --> 5
Keycode.SIX      --> 6
Keycode.SEVEN    --> 7
Keycode.EIGHT    --> 8
Keycode.NINE     --> 9
 
-------------------------------------------------------
7. F TUSLARI / F KEYS
-------------------------------------------------------
 
Keycode.F1    Keycode.F2    Keycode.F3    Keycode.F4
Keycode.F5    Keycode.F6    Keycode.F7    Keycode.F8
Keycode.F9    Keycode.F10   Keycode.F11   Keycode.F12
 
-------------------------------------------------------
8. OZEL TUSLAR / SPECIAL KEYS
-------------------------------------------------------
 
Keycode.ENTER          --> Enter
Keycode.ESCAPE         --> Esc
Keycode.BACKSPACE      --> TR: Geri sil      / EN: Backspace
Keycode.TAB            --> Tab
Keycode.SPACE          --> TR: Bosluk        / EN: Space bar
Keycode.DELETE         --> Delete
Keycode.INSERT         --> Insert
Keycode.HOME           --> TR: Satir basi    / EN: Home
Keycode.END            --> TR: Satir sonu    / EN: End
Keycode.PAGE_UP        --> TR: Sayfa yukari  / EN: Page Up
Keycode.PAGE_DOWN      --> TR: Sayfa asagi   / EN: Page Down
Keycode.CAPS_LOCK      --> TR: Buyuk harf kilidi / EN: Caps Lock
Keycode.PRINT_SCREEN   --> TR: Ekran goruntusu  / EN: Print Screen
 
-------------------------------------------------------
9. OK TUSLARI / ARROW KEYS
-------------------------------------------------------
 
Keycode.UP      --> TR: Yukari ok  / EN: Up arrow
Keycode.DOWN    --> TR: Asagi ok   / EN: Down arrow
Keycode.LEFT    --> TR: Sol ok     / EN: Left arrow
Keycode.RIGHT   --> TR: Sag ok    / EN: Right arrow
 
-------------------------------------------------------
10. MODIFIER TUSLAR / MODIFIER KEYS
-------------------------------------------------------
 
TR: Diger tuslarla birlikte basilir. Tek basina bir sey yapmaz.
EN: Pressed together with other keys. Does nothing alone.
 
Keycode.SHIFT           --> Shift (sol/left)
Keycode.RIGHT_SHIFT     --> Shift (sag/right)
Keycode.CONTROL         --> Ctrl (sol/left)
Keycode.RIGHT_CONTROL   --> Ctrl (sag/right)
Keycode.ALT             --> Alt (sol/left)
Keycode.RIGHT_ALT       --> Alt Gr (sag/right)
Keycode.WINDOWS         --> TR: Windows tusu    / EN: Windows key
Keycode.COMMAND         --> TR: Mac Command tusu / EN: Mac Command key
Keycode.GUI             --> TR: Win/Command (evrensel) / EN: Win/Command (universal)
Keycode.OPTION          --> TR: Mac Option tusu / EN: Mac Option key
 
-------------------------------------------------------
11. NUMPAD TUSLARI / NUMPAD KEYS
-------------------------------------------------------
 
Keycode.KEYPAD_ZERO           --> Numpad 0
Keycode.KEYPAD_ONE            --> Numpad 1
Keycode.KEYPAD_TWO            --> Numpad 2
Keycode.KEYPAD_THREE          --> Numpad 3
Keycode.KEYPAD_FOUR           --> Numpad 4
Keycode.KEYPAD_FIVE           --> Numpad 5
Keycode.KEYPAD_SIX            --> Numpad 6
Keycode.KEYPAD_SEVEN          --> Numpad 7
Keycode.KEYPAD_EIGHT          --> Numpad 8
Keycode.KEYPAD_NINE           --> Numpad 9
Keycode.KEYPAD_PLUS           --> Numpad +
Keycode.KEYPAD_MINUS          --> Numpad -
Keycode.KEYPAD_ASTERISK       --> Numpad *
Keycode.KEYPAD_FORWARD_SLASH  --> Numpad /
Keycode.KEYPAD_ENTER          --> Numpad Enter
Keycode.KEYPAD_PERIOD         --> Numpad .
Keycode.NUM_LOCK              --> Num Lock
 
-------------------------------------------------------
12. SES / MEDYA TUSLARI / MEDIA KEYS
-------------------------------------------------------
 
TR: Bu tuslar icin ekstra kutüphane gerekir:
EN: Extra library needed for these keys:
 
  from adafruit_hid.consumer_control import ConsumerControl
  from adafruit_hid.consumer_control_code import ConsumerControlCode
  cc = ConsumerControl(usb_hid.devices)
  cc.send(ConsumerControlCode.MUTE)
 
ConsumerControlCode.MUTE                --> TR: Sesi kapat      / EN: Mute
ConsumerControlCode.VOLUME_INCREMENT    --> TR: Sesi arttir     / EN: Volume Up
ConsumerControlCode.VOLUME_DECREMENT    --> TR: Sesi azalt      / EN: Volume Down
ConsumerControlCode.PLAY_PAUSE          --> TR: Oynat/Durdur    / EN: Play/Pause
ConsumerControlCode.SCAN_NEXT_TRACK     --> TR: Sonraki sarki   / EN: Next Track
ConsumerControlCode.SCAN_PREVIOUS_TRACK --> TR: Onceki sarki    / EN: Previous Track
 
-------------------------------------------------------
13. ORNEK KOD / EXAMPLE CODE
-------------------------------------------------------
 
  time.sleep(0.1)                        # 100ms bekle / wait
  kbd.press(Keycode.WINDOWS, Keycode.R)  # Win+R bas / press
  kbd.release_all()                      # Birak / release
  time.sleep(0.5)                        # Bekle / wait
  layout.write("notepad\n")             # notepad yaz + Enter / type + Enter
 
