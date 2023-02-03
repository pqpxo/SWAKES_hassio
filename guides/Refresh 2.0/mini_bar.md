# Home Assistant 2.0 - 'Mini Button Bar'

Below you will find the config in order to create the 'Mini Button Bar'. 

![enter image description here](https://i.imgur.com/j6Ue8GW.png)

This is created using the '[custom:button-card](https://github.com/custom-cards/button-card)' utilising the '[grid](https://github.com/custom-cards/button-card#advanced-styling-options)' feature to layout the 5 horizontal buttons (b1, b2, b3 ...).

Few things to mention before implementing in your own Home Assistant setup ...

 - You'll need to change the 'entity' value to something within your own Home Assistant instance (if you don't or use an invalid entity, it'll screw up the appearence/format of the button)
 
 - In regards to sizing ... I've very much customised and used specific values (shown below in config) for my own setup (designed around viewing on Google Pixel 6 Pro display). This means that it may look different or out of place for your own setup. I'd recommend tweaking the relevant element/s (Tweak > Save > Test/View > Tweak > Save > ...) until you get the desired outcome.
 - The button config below is designed to use/display 5 buttons horizontally within the 'bar'. If you want to add or remove any other buttons, you'll need to play around with a few different values (padding, width, height etc) to get it formatted correctly.

 <br> 

YAML Config:

   
    type: custom:button-card
    styles:
      card:
        - background-color: '#35425c'
        - border-radius: 20px
        - padding-left: 9px
        - box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px
      name:
        - font-size: 13px
      grid:
        - grid-template-areas: '"b1 b2 b3 b4 b5 "'
        - grid-template-columns: 1fr 1fr 1fr 1fr  1fr
        - grid-template-rows: 1fr
    custom_fields:
      b1:
        card:
          type: custom:button-card
          entity: group.living_room_power
          tap_action:
           action: toggle
          show_name: true
          name: Power
          icon: mdi:toggle-switch
          state:
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
              value: 'on'
            - icon: mdi:toggle-switch-off
              styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
                  - opacity: 0.3              
              operator: default         
      b2:
        card:
          type: custom:button-card
          entity: group.living_room_lamps
          tap_action:
           action: toggle	  
          show_name: true
          name: Lamps
          icon: mdi:lamps
          state:
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
              value: 'on'
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
                  - opacity: 0.3              
              operator: default  
      b3:
        card:
          type: custom:button-card
          show_name: true
          name: Ceiling
          entity: group.living_room_ceiling
          tap_action:
           action: toggle		  
          icon: mdi:ceiling-light-multiple
          state:
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
              value: 'on'
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
                  - opacity: 0.3              
              operator: default  
      b4:
        card:
          type: custom:button-card
          show_name: true
          entity: input_select.living_room_brightness
          tap_action:
           action: toggle		  
          name: Brightness
          icon: mdi:theme-light-dark
          state:
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
              value: 'on'
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
                  - opacity: 0.3              
              operator: default  
      b5:
        card:
          type: custom:button-card
          show_name: true
          name: Motion
          entity: automation.living_room_lights_motion
          tap_action:
           action: toggle	  
          icon: mdi:motion-sensor
          state:
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
              value: 'on'
            - styles:
                name:
                  - font-size: 10px
                  - padding-bottom: 5px
                card:
                  - background-color: '#2b374e'
                  - border-style: none
                  - border-radius: 15px
                  - width: 65px
                  - height: 65px
                icon:
                  - align-self: start
                  - text-align: start
                  - color: white
                  - opacity: 0.3              
              operator: default  


