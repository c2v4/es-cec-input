# es-cec-input
TV CEC remote control for Emulation Station (included in RetroPie)

# Features

* It will automatically map your retroarch keyboard config to the remote control buttons. ( See Supported Keyboard Key Below )

* It will not act on remote button presses when kodi or retroarch is running and will act as soon as ES returns or starts.


# Buttons

ES       <->         TV Remote

A        <->        SELECT or RED

B        <->        EXIT or GREEN

UP       <->        UP

DOWN     <->        DOWN

LEFT     <->        LEFT

RIGHT    <->        RIGHT

START    <->        FAST FORWARD or BLUE

SELECT   <->        REWIND OR YELLOW

# Dependencies
It depends on `python-uinput` package which contains the library and the udev rules at 
`/etc/udev/rules.d/40-uinput.rules` and also the `cec-utils` package. 

# Run the code as a non root user
You must first create the uinput group 

`sudo addgroup uinput`

Then add the pi user to the uinput group

`sudo adduser pi uinput`

# Autostart on boot
To start on boot, add to user's crontab. 

`crontab -e`

Add the line,

`@reboot hohup ./home/pi/PATH/TO/THE/SCRIPT/es-cec-input.py`


# Supported Keyboard Keys

As keys need to be mapped from retroarch.cfg supported keys to corresponding uinput keys not all the kesy are available. Most are supported, as seen below


Letters ("a" to "z"), left, right, up, down, enter, kp_enter, tab, insert, del, end, home, rshift, shift, ctrl, alt, space, escape, kp_plus, kp_minus, f1, f2, f3, f4, f5, f6, f7, f8, f9, f10, f11, f12,  num0, num1, num2, num3, num4, num5, num6, num7, num8, num9, pageup, pagedown, keypad0, keypad1, keypad2, keypad3, keypad4, keypad5, keypad6, keypad7, keypad8, keypad9, period, capslock, numlock, backspace, scroll_lock, backquote, pause, quote, comma, minus, slash, semicolon, equals, backslash, kp_period, kp_equals, rctrl, ralt

(where "kp_"# is for keypad keys)