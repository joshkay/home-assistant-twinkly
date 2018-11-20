# home-assistant-twinkly
Twinkly integration for home assistant

# Setup with hass.io
- Download twinkly.py to /config/python_scripts/
- Add the following switch config to configuration.yaml
- Make sure to replace TWINKLY_IP_HERE with the IP address of your twinkly lights (3 occurrences)

```
switch:
  - platform: command_line
    name: Twinkly
    switches:
      twinkly:
        command_on: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE on"
        command_off: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE off" 
        command_state: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE state"
        value_template: "{{ value == \"1\" }}"
        friendly_name: Twinkly
```