# home-assistant-twinkly
Twinkly integration for home assistant

# Setup with hass.io
- Download twinkly.py
- Change IP on line 11 to the IP of your twinkly lights
- Move twinkly.py to /config/python_scripts/
- Add the following switch config to configuration.yaml

```
switch:
  - platform: command_line
    name: Twinkly
    switches:
      twinkly:
        command_on: "python3 /config/python_scripts/twinkly.py on"
        command_off: "python3 /config/python_scripts/twinkly.py off" 
        command_state: "python3 /config/python_scripts/twinkly.py state"
        value_template: "{{ value == \"1\" }}"
        friendly_name: Twinkly
```