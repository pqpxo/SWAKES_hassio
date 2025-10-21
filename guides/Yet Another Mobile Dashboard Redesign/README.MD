

# Yet Another Mobile Dashboard Redesign

1) [**Title / Header Card**](#title--header-card)  
2) [**Stacked Notifications**](#stacked-notifications)  
3) [**Status Row**](#status-row)  
4) [**Broadcast Message**](#broadcast-message)  
5) [**TV Remote**](#tv-remote)
6) [**Button Rows**](#button-rows)

---

This whole process/setup took me several weeks/months to create so if you spot any errors or 'better ways of working' (thinking of custom:button-card templates maybe), please let me know by dropping me a message on Reddit, Facebook or the Home Assistant Community forum.

Also I've you've enjoyed this guide and want to show your appreciation some how, please [Buy Me A Coffee here](https://www.buymeacoffee.com/swakes)!
    
-   Reddit - [https://old.reddit.com/user/swake88/submitted/](https://old.reddit.com/user/swake88/submitted/)
    
-   Blog - [https://makes.swakes.co.uk](https://makes.swakes.co.uk/?fbclid=IwAR2C_NhUkD9BoStN323iteVV36vM665RzfQYAS8BplibtuTl-dT28h2thPM)
    
-   Pastebin - [https://pastebin.com/u/pqpxoxa](https://pastebin.com/u/pqpxoxa?fbclid=IwAR38cCRP1sUIKekn6e8RAer11AkLDKm-eTOGOLhQGK5ieFWaaFDZ6g1QdEw)
    
-   BMAC - [https://www.buymeacoffee.com/swakes](https://www.buymeacoffee.com/swakes?fbclid=IwAR2C0bO2Ag_xclFUWKKHTU2TTmgFTnfBex8O8tJrV8YUXCcnp-LrGLUPgfY)
- HA Community - https://community.home-assistant.io/u/pqpxd

---

**Please Note:** All of these cards are contained within a single **vertical-stack** card on the dashboard, rather than being placed in separate sections.

<br>

## Title / Header Card
<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/titleheader.png" />
</p>
<b>Required</b>: custom:button-card

    type: custom:button-card
    name: |
      [[[ return `Welcome ${user.name}`; ]]]
    show_label: true
    label: >-
      [[[ const now = new Date(); const options = { weekday: "short", day:
      "2-digit", month: "short" }; return now.toLocaleString("en-GB",
      options).replace(",", "") + "&nbsp;&nbsp;" + now.toLocaleTimeString("en-GB", {
      hour: "2-digit", minute: "2-digit", hour12: true }); ]]]
    double_tap_action:
      action: navigate
      navigation_path: /dashboard-v2/overview?disable_km
    styles:
      card:
        - background-color: transparent
        - padding: 1px
        - border-style: none
        - margin-top: "-11px"
        - margin-bottom: "-2px"
      grid:
        - grid-template-areas: " \"n ps pn\" \"l ps pn\""
        - grid-template-columns: 70% 15% 15%
        - grid-template-rows: 1fr min-content
        - gap: 0px 0px
      name:
        - font-size: 44px
        - justify-self: left
        - letter-spacing: "-2.3px"
        - font-weight: bold
        - padding-left: 6px
        - padding-top: 5px
      label:
        - font-size: 22px
        - justify-self: left
        - letter-spacing: "-1px"
        - font-weight: 400
        - padding-left: 10px
    custom_fields:
      ps:
        card:
          type: custom:button-card
          color: transparent
          entity: person.swakes
          show_entity_picture: true
          tap_action:
            action: none
          show_name: false
          show_icon: true
          styles:
            card:
              - background-color: "#4b5975"
              - border-radius: 50px
              - width: 60px
              - height: 60px
              - border-style: none
              - padding: 8px
              - box-shadow: >-
                  rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 2px 13px
                  -1px, rgba(0, 0, 0, 0.2) 0px -3px 5px inset !important;
              - overflow: visible
            icon:
              - width: 38px
              - height: 38px
            custom_fields:
              box:
                - position: absolute
                - left: 14%
                - top: 84%
                - transform: translate(-50%, -50%)
                - z-index: 9999
                - overflow: visible
                - width: 18px
                - height: 18px
          custom_fields:
            box:
              card:
                type: custom:button-card
                icon: mdi:home
                entity: person.swakes
                show_name: false
                state:
                  - styles:
                      card:
                        - background-color: transparent
                        - border-style: none
                        - border-radius: 50px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - width: 20px
                        - height: 20px
                        - overflow: visible
                      icon:
                        - width: 14px
                        - height: 14px
                        - background-color: green
                        - color: white
                        - border-radius: 50%
                        - padding: 2px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - z-index: 9999
                    value: home
                  - styles:
                      card:
                        - background-color: transparent
                        - border-style: none
                        - border-radius: 50px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - width: 20px
                        - height: 20px
                        - overflow: visible
                      icon:
                        - width: 14px
                        - height: 14px
                        - background-color: red
                        - color: white
                        - border-radius: 50%
                        - padding: 2px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - z-index: 9999
                    operator: default
      pn:
        card:
          type: custom:button-card
          color: transparent
          entity: person.nabila
          show_entity_picture: true
          tap_action:
            action: none
          show_name: false
          show_icon: true
          styles:
            card:
              - background-color: "#4b5975"
              - border-radius: 50px
              - width: 60px
              - height: 60px
              - border-style: none
              - padding: 8px
              - box-shadow: >-
                  rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 2px 13px
                  -1px, rgba(0, 0, 0, 0.2) 0px -3px 5px inset !important;
              - overflow: visible
            icon:
              - width: 38px
              - height: 38px
            custom_fields:
              box:
                - position: absolute
                - left: 14%
                - top: 84%
                - transform: translate(-50%, -50%)
                - z-index: 9999
                - overflow: visible
                - width: 18px
                - height: 18px
          custom_fields:
            box:
              card:
                type: custom:button-card
                icon: mdi:home
                entity: person.nabila
                show_name: false
                state:
                  - styles:
                      card:
                        - background-color: transparent
                        - border-style: none
                        - border-radius: 50px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - width: 20px
                        - height: 20px
                        - overflow: visible
                      icon:
                        - width: 14px
                        - height: 14px
                        - background-color: green
                        - color: white
                        - border-radius: 50%
                        - padding: 2px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - z-index: 9999
                    value: home
                  - styles:
                      card:
                        - background-color: transparent
                        - border-style: none
                        - border-radius: 50px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - width: 20px
                        - height: 20px
                        - overflow: visible
                      icon:
                        - width: 14px
                        - height: 14px
                        - background-color: red
                        - color: white
                        - border-radius: 50%
                        - padding: 2px
                        - display: flex
                        - justify-content: center
                        - align-items: center
                        - z-index: 9999
                    operator: default


## Stacked Notifications
<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/Screenshot_20251020-145249.png" />
</p>
<b>Required</b>: custom:button-card / custom:mod-card

For a more detailed guide [check out this post](https://old.reddit.com/r/homeassistant/comments/1mvck5r/stacked_notifications/).

    type: custom:mod-card
    card:
      type: vertical-stack
      cards:
        - type: custom:button-card
          template: notification_card
          show_entity_picture: true
          entity_picture: /local/halogo.png
          label: No notifications to display
          variables:
            icon_bg: "#35425c"
            badge_bg: "#f59e0b"
            badge_icon: mdi:clock-alert-outline
            card_name: No Notifications
          styles:
            card:
              - background-color: "#35425c"
              - border: 1px solid rgba(36, 46, 66, 0.5)
              - border-radius: 24px
              - padding: 12px
            label:
              - padding-top: 2px
            name:
              - font-size: 16px
              - font-weight: bold
            icon:
              - padding: 5px
              - border-radius: 50%
              - border: none
              - width: 35px
              - background-color: "#35425c"
          card_mod:
            style: |
              /* Hide the dismiss X for this card only */
              ha-card mwc-icon-button,
              ha-card ha-icon-button,
              ha-card .dismiss,
              ha-card .dismiss-btn,
              ha-card .dismiss_button {
                display: none !important;
              }
        - type: conditional
          conditions:
            - condition: state
              entity: sensor.notification_updates_available_count
              state_not: "0"
            - condition: state
              entity: input_boolean.notification_updates_available_dismissed
              state: "off"
          card:
            type: custom:button-card
            template: notification_card
            show_entity_picture: true
            entity_picture: /local/halogo.png
            tap_action:
              action: navigate
              navigation_path: /config/dashboard
            label: |
              [[[
                const text = states['sensor.notification_updates_available_count'].state;
                // if the state matches the format "'NAME' requires updating"
                const match = text.match(/^'(.*)' requires updating$/);
                if (match) {
                  return `<b>'${match[1]}'</b> requires updating`;
                } else {
                  return text; // fallback for "3 updates available" or "0"
                }
              ]]]
            variables:
              icon_bg: "#35425c"
              badge_bg: "#f59e0b"
              badge_icon: mdi:clock-alert-outline
              entity: sensor.notification_updates_available_count
              card_name: Available Updates
              dismiss_helper: input_boolean.notification_updates_available_dismissed
              dismiss_until: input_datetime.notification_updates_available_until
            styles:
              card:
                - background-color: "#35425c"
                - border: 1px solid rgba(36, 46, 66, 0.5)
                - border-radius: 24px
                - padding: 12px
              label:
                - padding-top: 2px
              name:
                - font-size: 16px
                - font-weight: bold
              icon:
                - padding: 5px
                - border-radius: 50%
                - border: none
                - width: 35px
                - background-color: "#35425c"
        - type: conditional
          conditions:
            - condition: numeric_state
              entity: sensor.pixel_fold_battery_level
              below: 25
            - condition: state
              entity: input_boolean.notify_roborock_dismissed
              state: "off"
          card:
            type: custom:button-card
            template: notification_card
            show_entity_picture: true
            entity_picture: /local/pixelfoldphone.png
            label: Pixel Fold battery is low. Please charge soon
            variables:
              icon_bg: "#35425c"
              badge_bg: "#ff6467"
              badge_icon: mdi:alert-circle
              entity: sensor.pixel_fold_battery_level
              card_name: Pixel Fold Battery
              dismiss_helper: input_boolean.notify_roborock_dismissed
              dismiss_until: input_datetime.notify_roborock_until
            styles:
              card:
                - background-color: "#35425c"
                - border: 1px solid rgba(36, 46, 66, 0.5)
                - border-radius: 24px
                - padding: 12px
              label:
                - padding-top: 2px
              name:
                - font-size: 16px
                - font-weight: bold
              icon:
                - padding: 5px
                - border-radius: 50%
                - width: 35px
        - type: conditional
          conditions:
            - condition: numeric_state
              entity: sensor.google_pixel_watch_2_battery_level
              below: 55
            - condition: state
              entity: input_boolean.notify_pixel_watch_battery_dismissed
              state: "off"
          card:
            type: custom:button-card
            template: notification_card
            show_entity_picture: true
            entity_picture: /local/pixelwatch2.png
            label: Pixel Watch battery is low. Please charge soon
            variables:
              icon_bg: "#35425c"
              badge_bg: "#ff6467"
              badge_icon: mdi:alert-circle
              entity: sensor.pixel_fold_battery_level
              card_name: Pixel Watch Battery
              dismiss_helper: input_boolean.notify_pixel_watch_battery_dismissed
              dismiss_until: input_datetime.notify_pixel_watch_battery_until
            styles:
              card:
                - background-color: "#35425c"
                - border: 1px solid rgba(36, 46, 66, 0.5)
                - border-radius: 24px
                - padding: 12px
              label:
                - padding-top: 2px
              name:
                - font-size: 16px
                - font-weight: bold
              icon:
                - padding: 5px
                - width: 35px
                - border-radius: 50%
        - type: conditional
          conditions:
            - condition: state
              entity: light.floor_lamps
              state: "on"
            - condition: state
              entity: media_player.65_qled_2
              state_not: "on"
            - condition: state
              entity: input_boolean.notify_livingroom_lights_dismissed
              state: "off"
          card:
            type: custom:button-card
            template: notification_card
            show_entity_picture: true
            entity_picture: /local/ikeafloorlamp.png
            label: The Living Room lights have been left on.
            variables:
              icon_bg: "#35425c"
              badge_bg: "#f59e0b"
              badge_icon: mdi:clock-alert-outline
              entity: light.floor_lamps
              card_name: Living Room Lights
              dismiss_helper: input_boolean.notify_livingroom_lights_dismissed
              dismiss_until: input_datetime.notify_livingroom_lights_until
            styles:
              card:
                - background-color: "#35425c"
                - border: 1px solid rgba(36, 46, 66, 0.5)
                - border-radius: 24px
                - padding: 12px
              label:
                - padding-top: 2px
              name:
                - font-size: 16px
                - font-weight: bold
              icon:
                - padding: 5px
                - border-radius: 50%
                - border: none
                - width: 35px
                - background-color: "#35425c"
        - type: conditional
          conditions:
            - condition: state
              entity: binary_sensor.nighttime
              state: "on"
            - condition: state
              entity: input_boolean.push_notification_toggle
              state: "off"
            - condition: state
              entity: input_boolean.notify_push_alert_dismissed
              state: "off"
          card:
            type: custom:button-card
            template: notification_card
            show_entity_picture: true
            entity_picture: /local/pushover.png
            label: Motion push alerts are not enabled
            variables:
              icon_bg: "#35425c"
              badge_bg: "#facc15"
              badge_icon: mdi:battery-alert
              entity: input_boolean.push_notification_toggle
              card_name: Motion Push Alerts
              dismiss_helper: input_boolean.notify_push_alert_dismissed
              dismiss_until: input_datetime.notify_push_alert_until
            styles:
              card:
                - background-color: "#35425c"
                - border: 1px solid rgba(36, 46, 66, 0.5)
                - border-radius: 24px
                - padding: 12px
              label:
                - padding-top: 2px
              name:
                - font-size: 16px
                - font-weight: bold
              icon:
                - padding: 5px
                - border-radius: 50%
                - width: 35px
    grid_options:
      columns: 24
      rows: auto
    card_mod:
      style:
        hui-vertical-stack-card$: |
          hui-card {
            position: relative;
            border-radius: 58px;
            transition: all 0.3s ease;
            border: none;
            margin-bottom: 4px;
          }
          /* Stacked (only when next card is visible) */
          hui-card:not([hidden]) ~ hui-card:not([hidden]) {
            margin-top: -67px;
            box-shadow: >-
                    rgba(0, 0, 0, 0.2) 0px 2px 4px, rgba(0, 0, 0, 0.15) 0px 2px 10px
                    -1px, rgba(0, 0, 0, 0.1) 0px -2px 4px inset !important; 
          }
          /* Blur all but the last visible */
          hui-card:has(~ hui-card:not([hidden])) {
            filter: blur(0.6px);
            
          }
          /* The last/top visible card stays clear */
          hui-card:not(:has(~ hui-card:not([hidden]))) {
            filter: none;
            
            background: var(--card-background-color);
          }
          /* On hover/active → unstack and clear ALL */
          :host(:hover) hui-card,
          :host(:active) hui-card {
            margin-top: 0 !important;
            box-shadow: none !important;
            filter: none !important;
            
          }


## Status Row

<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/Screenshot%202025-10-20%20144404.png" />
</p>
<b>Required</b>: custom:button-card 

    type: horizontal-stack
    cards:
      - type: custom:button-card
        color_type: blank-card
        styles:
          card:
            - width: px
      - type: custom:button-card
        name: Doors
        label: Closed
        entity: binary_sensor.front_door_contact
        icon: mdi:lock
        show_state: false
        show_name: true
        show_label: true
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          label:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        name: Lights
        entity: sensor.any_all_lights_on
        icon: phu:bulb-group
        show_state: true
        show_name: true
        show_label: false
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          state:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        name: Media
        entity: sensor.active_media_players_count_2
        icon: mdi:monitor-speaker
        label: "Off"
        show_state: true
        show_name: true
        show_label: false
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          state:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        name: Sensors
        entity: binary_sensor.front_door_contact
        icon: mdi:motion-sensor
        label: Online
        show_state: false
        show_name: true
        show_label: true
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          label:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        name: HA
        entity: sensor.addons_overall_status
        icon: mdi:home-assistant
        show_state: true
        show_name: true
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          state:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        name: Network
        entity: binary_sensor.front_door_contact
        icon: mdi:lan
        label: Online
        show_state: false
        show_name: true
        show_label: true
        styles:
          card:
            - background-color: transparent
            - border-style: none
            - padding: 5px
          label:
            - justify-self: center
            - font-size: 13px
            - align-self: start
            - font-weight: 400
            - letter-spacing: "-0.5px"
            - padding-top: 3px
          name:
            - justify-self: center
            - font-size: 17px
            - align-self: start
            - font-weight: bold
            - letter-spacing: "-0.5px"
            - padding-top: 7px
          icon:
            - align-self: center
            - width: 30px
            - height: 30px
            - color: white
            - background-color: "#35425c"
            - border-radius: 24px
            - padding: 15px
          img_cell:
            - justify-content: center
            - align-self: center
      - type: custom:button-card
        color_type: blank-card
        styles:
          card:
            - width: px


## Broadcast Message

<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/Screenshot_20251020-144346.png" />
</p>

**Required**: *input_select* entity for room selection (In my instance I have 'Living Room', 'Kitchen' and 'Bedroom')
<b>Required</b>: custom:button-card / custom:bubble-card


    type: vertical-stack
    cards:
      - type: custom:bubble-card
        card_type: pop-up
        hash: "#broadcast2"
        show_header: false
        button_type: name
        card_layout: normal
        name: Living Room
        margin_top_mobile: 335px
        margin_top_desktop: calc(100vh - 400px)
        icon: mdi:sofa
        style: |
    
          .bubble-button-card-container {
            border-radius: 32px;
          {
    
          .bubble-pop-up {
            width: calc(100% - 20px) !important;
            margin-left: 20px !important;
            margin-right: 20px !important;
          }  
        show_name: false
        scrolling_effect: false
        background_update: false
        close_on_click: true
        bg_opacity: "70"
        bg_blur: "40"
        width_desktop: 440px
        shadow_opacity: "40"
        margin: 10px
        styles: ""
        backdrop_blur: "0"
      - type: grid
        columns: 1
        square: false
        cards:
          - type: custom:button-card
            name: Select Speaker
            show_label: false
            show_name: true
            styles:
              card:
                - background-color: transparent
                - padding: 10px
                - border-radius: 24px
                - border-style: none
              grid:
                - grid-template-areas: "\"n r1 r2 r3\" \"blk blk blk blk\" \"rm rm rm rm\""
                - grid-template-columns: 52% 15% 15% 15%
                - grid-template-rows: min-content min-content 1fr
                - gap: 5px 5px
              name:
                - font-weight: 450
                - font-size: 34px
                - align-self: center
                - letter-spacing: "-1.2px"
                - justify-self: start
                - padding-left: 10px
            custom_fields:
              blk:
                card:
                  type: custom:button-card
                  color_type: blank-card
                  styles:
                    card:
                      - height: 10px
              r1:
                card:
                  type: custom:button-card
                  entity: input_select.speaker_room_choice
                  name: false
                  show_name: false
                  icon: mdi:sofa
                  state:
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                        icon:
                          - color: white
                          - width: 35px
                      value: Living Room
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                          - opacity: 0.6
                        icon:
                          - color: white
                          - width: 35px
                          - opacity: 0.6
                      operator: default
                  tap_action:
                    action: call-service
                    service: input_select.select_option
                    service_data:
                      entity_id: input_select.speaker_room_choice
                      option: Living Room
              r2:
                card:
                  type: custom:button-card
                  entity: input_select.speaker_room_choice
                  name: false
                  show_name: false
                  icon: mdi:fridge
                  state:
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                        icon:
                          - color: white
                          - width: 35px
                      value: Kitchen
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                          - opacity: 0.6
                        icon:
                          - color: white
                          - width: 35px
                          - opacity: 0.6
                      operator: default
                  tap_action:
                    action: call-service
                    service: input_select.select_option
                    service_data:
                      entity_id: input_select.speaker_room_choice
                      option: Kitchen
              r3:
                card:
                  type: custom:button-card
                  entity: input_select.speaker_room_choice
                  name: false
                  show_name: false
                  icon: mdi:bed-king
                  state:
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                        icon:
                          - color: white
                          - width: 35px
                      value: Bedroom
                    - styles:
                        card:
                          - background-color: "#4b5975"
                          - border-style: none
                          - border-radius: 20px
                          - width: 60px
                          - height: 60px
                          - opacity: 0.6
                        icon:
                          - color: white
                          - width: 35px
                          - opacity: 0.6
                      operator: default
                  tap_action:
                    action: call-service
                    service: input_select.select_option
                    service_data:
                      entity_id: input_select.speaker_room_choice
                      option: Bedroom
              rm:
                card:
                  type: vertical-stack
                  cards:
                    - type: horizontal-stack
                      cards:
                        - type: custom:button-card
                          name: Put The <br>Kettle On
                          icon: mdi:kettle-steam
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 2px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999
                        - type: custom:button-card
                          color_type: blank-card
                          styles:
                            card:
                              - width: 1px
                        - type: custom:button-card
                          name: Down In 5 Minutes
                          icon: mdi:run-fast
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 2px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999
                    - type: custom:button-card
                      color_type: blank-card
                      styles:
                        card:
                          - height: px
                    - type: horizontal-stack
                      cards:
                        - type: custom:button-card
                          name: Check Your Phone
                          icon: mdi:cellphone-message
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 2px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999
                        - type: custom:button-card
                          color_type: blank-card
                          styles:
                            card:
                              - width: 1px
                        - type: custom:button-card
                          name: Someone's At The Door
                          icon: mdi:doorbell-video
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 0px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999
                    - type: custom:button-card
                      color_type: blank-card
                      styles:
                        card:
                          - height: px
                    - type: horizontal-stack
                      cards:
                        - type: custom:button-card
                          name: Bring Down Washing
                          icon: mdi:washing-machine
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 2px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999
                        - type: custom:button-card
                          color_type: blank-card
                          styles:
                            card:
                              - width: 1px
                        - type: custom:button-card
                          name: Dinner Is <br>Ready
                          icon: mdi:food-turkey
                          show_state: false
                          show_name: true
                          show_icon: true
                          styles:
                            grid:
                              - grid-template-areas: "\"i n\""
                              - grid-template-columns: auto auto
                              - grid-template-rows: auto
                              - gap: 0px 0px
                            card:
                              - padding: 15px
                              - border-radius: 20px
                              - background-color: "#4b5975"
                              - border-style: none
                              - width: 205px
                            name:
                              - justify-self: start
                              - align-self: start
                              - letter-spacing: "-1.02px"
                              - font-size: 22px
                              - padding-left: px
                              - padding-top: 8px
                              - font-weight: 500
                              - white-space: normal
                              - overflow: visible
                              - text-overflow: unset
                              - word-break: break-word
                            icon:
                              - background-color: transparent
                              - color: white
                              - width: 60px
                              - border-radius: 50%
                              - padding: 0px
                              - display: flex
                              - justify-content: center
                              - align-items: center
                              - z-index: 9999


## TV Remote

<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/Screenshot_20251020-144321.png" />
</p>
<b>Required</b>: custom:button-card , custom:bubble-card


    type: vertical-stack
    cards:
      - type: custom:bubble-card
        card_type: pop-up
        hash: "#remote"
        show_header: false
        button_type: name
        card_layout: normal
        name: Living Room
        margin_top_mobile: 235px
        margin_top_desktop: calc(100vh - 400px)
        icon: mdi:sofa
        style: |
    
          .bubble-button-card-container {
            border-radius: 32px;
          {
    
          .bubble-pop-up {
            width: calc(100% - 20px) !important;
            margin-left: 20px !important;
            margin-right: 20px !important;
          }  
        show_name: false
        scrolling_effect: false
        background_update: false
        close_on_click: true
        bg_opacity: "70"
        bg_blur: "40"
        width_desktop: 440px
        shadow_opacity: "40"
        margin: 10px
        styles: ""
        backdrop_blur: "0"
      - type: grid
        columns: 1
        square: false
        cards:
          - type: custom:button-card
            name: Remote
            label: Samsung QE65Q80D
            show_label: true
            styles:
              card:
                - background-color: transparent
                - padding: 2px
                - padding-left: 25px
                - border: none
                - margin-bottom: "-20px"
                - margin-top: 5px
              grid:
                - grid-template-areas: " \"ic n\" \"ic l \""
                - grid-template-columns: 25% 75%
                - grid-template-rows: 1fr 1fr
                - gap: 0px 15px
              name:
                - font-size: 34px
                - justify-self: start
                - font-weight: 500
                - align-items: start
                - padding-top: px
                - letter-spacing: "-0.7px"
                - align-self: end
              label:
                - font-size: 18px
                - justify-self: left
                - letter-spacing: "-0.7px"
                - font-weight: 400
                - padding-bottom: 6px
                - padding-left: 2px
            custom_fields:
              ic:
                card:
                  type: custom:button-card
                  show_name: false
                  icon: mdi:sofa-outline
                  entity_picture: /local/samsungtv.png
                  show_entity_picture: true
                  styles:
                    card:
                      - background-color: transparent
                      - border-style: none
                      - padding-left: 5px
                    icon:
                      - align-self: end
                      - color: white
                      - width: 100px
                      - padding-left: 0px
                      - padding-bottom: 10px
                    img_cell:
                      - justify-content: start
                      - align-self: start
                      - margin: none
          - type: horizontal-stack
            cards:
              - type: custom:button-card
                color_type: blank-card
                styles:
                  card:
                    - width: 10px
              - type: custom:button-card
                styles:
                  grid:
                    - grid-template-areas: >-
                        "power source blank  channelnumber channelnumber" "dpad dpad
                        dpad  volstack chanstk" "dpad dpad dpad  volstack chanstk"
                        "dpad dpad dpad  volstack chanstk" "home return exit guide
                        subtitles  " "rewind play pause  stop forward"  
                    - grid-template-columns: 65px 65px 65px 65px 65px
                    - grid-template-rows: 65px 65px 65px 65px 65px 65px
                    - row-gap: 8px
                    - column-gap: 8px
                  card:
                    - background: transparent
                    - border-style: none
                    - padding: 20px
                    - margin: 0
                custom_fields:
                  subtitles:
                    card:
                      type: custom:button-card
                      icon: mdi:subtitles-outline
                      tap_action:
                        action: call-service
                        service: script.send_samsung_subtitles
                      show_name: false
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  home:
                    card:
                      type: custom:button-card
                      icon: mdi:home
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_home
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  guide:
                    card:
                      type: custom:button-card
                      icon: mdi:television-guide
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_guide
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  return:
                    card:
                      type: custom:button-card
                      icon: mdi:undo
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_return
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  exit:
                    card:
                      type: custom:button-card
                      icon: mdi:exit-to-app
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_exit
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  dpad:
                    card:
                      type: custom:button-card
                      styles:
                        grid:
                          - grid-template-areas: "\". up .\" \"left ok right\" \". down .\""
                          - grid-template-columns: 65px 65px 65px
                          - grid-template-rows: 65px 65px 65px
                          - row-gap: 0px
                          - column-gap: 0px
                        card:
                          - background: transparent
                          - padding: 0
                          - margin: 0
                          - border: none
                      custom_fields:
                        up:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-up
                            tap_action:
                              action: call-service
                              service: script.send_samsung_up
                            show_name: false
                            styles:
                              card:
                                - width: 65px
                                - height: 65px
                                - margin: 0
                                - padding: 0
                                - border: none
                                - box-shadow: none
                                - background-color: "#4b5975"
                                - border-top-left-radius: 22px
                                - border-top-right-radius: 22px
                                - border-bottom-left-radius: 0px
                                - border-bottom-right-radius: 0px
                              icon:
                                - background-color: transparent
                                - color: white
                                - width: 32px
                                - height: 32px
                        left:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-left
                            tap_action:
                              action: call-service
                              service: script.send_samsung_left
                            show_name: false
                            styles:
                              card:
                                - width: 65px
                                - height: 65px
                                - margin: 0
                                - padding: 0
                                - border: none
                                - box-shadow: none
                                - background-color: "#4b5975"
                                - border-top-left-radius: 22px
                                - border-bottom-left-radius: 22px
                                - border-top-right-radius: 0px
                                - border-bottom-right-radius: 0px
                              icon:
                                - background-color: transparent
                                - color: white
                                - width: 32px
                                - height: 32px
                        ok:
                          card:
                            type: custom:button-card
                            icon: mdi:checkbox-blank-circle-outline
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_ok
                            styles:
                              card:
                                - width: 65px
                                - height: 65px
                                - margin: 0
                                - padding: 0
                                - border: none
                                - box-shadow: none
                                - background-color: "#4b5975"
                                - border-radius: 0px
                              icon:
                                - background-color: transparent
                                - color: white
                                - width: 32px
                                - height: 32px
                        right:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-right
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_right
                            styles:
                              card:
                                - width: 65px
                                - height: 65px
                                - margin: 0
                                - padding: 0
                                - border: none
                                - box-shadow: none
                                - background-color: "#4b5975"
                                - border-top-right-radius: 22px
                                - border-bottom-right-radius: 22px
                                - border-top-left-radius: 0px
                                - border-bottom-left-radius: 0px
                              icon:
                                - background-color: transparent
                                - color: white
                                - width: 32px
                                - height: 32px
                        down:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-down
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_down
                            styles:
                              card:
                                - width: 65px
                                - height: 65px
                                - margin: 0
                                - padding: 0
                                - border: none
                                - box-shadow: none
                                - background-color: "#4b5975"
                                - border-bottom-left-radius: 22px
                                - border-bottom-right-radius: 22px
                                - border-top-left-radius: 0px
                                - border-top-right-radius: 0px
                              icon:
                                - background-color: transparent
                                - color: white
                                - width: 32px
                                - height: 32px
                  volstack:
                    card:
                      type: custom:button-card
                      styles:
                        grid:
                          - grid-template-areas: "\"volup\" \"mute\" \"voldown\""
                          - grid-template-rows: 65px 65px 65px
                          - row-gap: 0px
                        card:
                          - background: transparent
                          - padding: 0
                          - margin: 0
                          - border: none
                      custom_fields:
                        volup:
                          card:
                            type: custom:button-card
                            icon: mdi:volume-plus
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_volup
                            styles:
                              card:
                                - width: 62px
                                - height: 62px
                                - background-color: "#4b5975"
                                - border-top-left-radius: 22px
                                - border-top-right-radius: 22px
                                - border-bottom-left-radius: 0px
                                - border-bottom-right-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                        mute:
                          card:
                            type: custom:button-card
                            icon: mdi:volume-off
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_volmute
                            styles:
                              card:
                                - width: 62px
                                - height: 68px
                                - background-color: "#4b5975"
                                - border-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                        voldown:
                          card:
                            type: custom:button-card
                            icon: mdi:volume-minus
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_voldown
                            styles:
                              card:
                                - width: 62px
                                - height: 62px
                                - background-color: "#4b5975"
                                - border-bottom-left-radius: 22px
                                - border-bottom-right-radius: 22px
                                - border-top-left-radius: 0px
                                - border-top-right-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                  chanstk:
                    card:
                      type: custom:button-card
                      styles:
                        grid:
                          - grid-template-areas: "\"channelup\" \"guide\" \"channeldown\""
                          - grid-template-rows: 65px 65px 65px
                          - row-gap: 0px
                        card:
                          - background: transparent
                          - padding: 0
                          - margin: 0
                          - border: none
                      custom_fields:
                        channelup:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-up
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_chanup
                            styles:
                              card:
                                - width: 62px
                                - height: 62px
                                - background-color: "#4b5975"
                                - border-top-left-radius: 22px
                                - border-top-right-radius: 22px
                                - border-bottom-left-radius: 0px
                                - border-bottom-right-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                        guide:
                          card:
                            type: custom:button-card
                            icon: mdi:television-guide
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_guide
                            styles:
                              card:
                                - width: 62px
                                - height: 68px
                                - background-color: "#4b5975"
                                - border-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                        channeldown:
                          card:
                            type: custom:button-card
                            icon: mdi:chevron-down
                            show_name: false
                            tap_action:
                              action: call-service
                              service: script.send_samsung_chandown
                            styles:
                              card:
                                - width: 62px
                                - height: 62px
                                - background-color: "#4b5975"
                                - border-bottom-left-radius: 22px
                                - border-bottom-right-radius: 22px
                                - border-top-left-radius: 0px
                                - border-top-right-radius: 0px
                                - border: none
                                - box-shadow: none
                                - padding: 0
                                - margin: 0
                              icon:
                                - color: white
                                - background-color: transparent
                                - width: 32px
                                - height: 32px
                  power:
                    card:
                      type: custom:button-card
                      icon: mdi:power
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_power
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  blank:
                    card:
                      type: custom:button-card
                      icon: mdi:plex
                      show_name: false
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  source:
                    card:
                      type: custom:button-card
                      icon: mdi:video-input-hdmi
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_source
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  channelnumber:
                    card:
                      type: custom:button-card
                      icon: mdi:numeric
                      show_name: false
                      styles:
                        card:
                          - height: 61.992px
                          - margin: 0
                          - padding: 0
                          - background-color: "#4b5975"
                          - border-radius: 22px
                          - border: none
                          - box-shadow: none
                        icon:
                          - background-color: transparent
                          - color: white
                          - width: 32px
                          - height: 32px
                  rewind:
                    card:
                      type: custom:button-card
                      icon: mdi:rewind
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_rewind
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  play:
                    card:
                      type: custom:button-card
                      icon: mdi:play
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_play
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  pause:
                    card:
                      type: custom:button-card
                      icon: mdi:pause
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_pause
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  stop:
                    card:
                      type: custom:button-card
                      icon: mdi:stop
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_stop
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px
                  forward:
                    card:
                      type: custom:button-card
                      icon: mdi:fast-forward
                      show_name: false
                      tap_action:
                        action: call-service
                        service: script.send_samsung_forward
                      styles:
                        card:
                          - width: 62px
                          - height: 62px
                          - background-color: "#4b5975"
                          - border: none
                          - margin: 0
                          - border-radius: 22px
                        icon:
                          - width: 32px
                          - height: 32px
                          - color: white
                          - background-color: transparent
                          - padding: 6px

## Button Rows

<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/Screenshot_20251020-151455(1).png" />
</p>
<b>Required</b>: custom:button-card

**<br>**

Example shown is the 'Lights' card/row
**<br>**

    type: custom:button-card
    name: Lights
    entity: sensor.house_lights_on_count
    show_state: true
    show_name: true
    entity_picture: /local/alllightshouselogo.png
    show_entity_picture: true
    styles:
      card:
        - background-color: "#35425c"
        - border-radius: 24px
        - border-style: none
        - padding: 1px 3px 15px 3px
        - height: 63.965px
      grid:
        - grid-template-areas: "\"i n bt bs\" \"i s bt bs\""
        - grid-template-columns: 0.5fr 1fr auto min-content
        - grid-template-rows: min-content min-content
        - gap: 2px 0px
      name:
        - letter-spacing: "-0.5px"
        - font-weight: bold
        - font-size: 20px
        - justify-self: start
        - align-self: end
      state:
        - letter-spacing: "-0.5px"
        - font-weight: 400
        - font-size: 15px
        - align-self: start
        - justify-self: start
      icon:
        - align-self: center
        - width: 34px
        - height: 34px
        - color: white
        - background-color: transparent
        - border-radius: 50px
        - padding: 2px
      img_cell:
        - justify-content: center
        - align-self: center
    custom_fields:
      bt:
        card:
          type: custom:button-card
          styles:
            card:
              - border-radius: 18px
              - padding: 8px
              - border: none
              - background-color: transparent
            grid:
              - grid-template-areas: "\"home lock shield away privacy\""
              - grid-template-columns: 1fr 1fr 1fr 1fr 1fr
              - column-gap: 6px
          custom_fields:
            home:
              card:
                type: custom:button-card
                entity: light.ground_hallway_ceiling_lights_2
                icon: mdi:stairs
                show_name: false
                styles:
                  card:
                    - border-radius: 50px
                    - opacity: 0
                    - border: none
                    - background-color: "#4B5975"
                    - width: 48px
                    - height: 46px
                  icon:
                    - color: white
                    - width: 24px
            lock:
              card:
                type: custom:button-card
                entity: light.ground_hallway_ceiling_lights
                icon: mdi:stairs
                show_name: false
                state:
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                    value: "on"
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                        - opacity: 0.3
                    value: "off"
            shield:
              card:
                type: custom:button-card
                entity: light.kitchen_ceiling_lights
                icon: mdi:fridge
                show_name: false
                state:
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                    value: "on"
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                        - opacity: 0.3
                    value: "off"
            away:
              card:
                type: custom:button-card
                entity: light.living_room_lights
                icon: mdi:sofa
                show_name: false
                state:
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                    value: "on"
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                        - opacity: 0.3
                    value: "off"
            privacy:
              card:
                type: custom:button-card
                entity: light.office_lights
                icon: mdi:desk
                show_name: false
                state:
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                    value: "on"
                  - styles:
                      card:
                        - border-radius: 50px
                        - border: none
                        - background-color: "#4B5975"
                        - width: 48px
                        - height: 46px
                      icon:
                        - color: white
                        - width: 24px
                        - opacity: 0.3
                    value: "off"
      bs:
        card:
          type: custom:button-card
          color_type: blank-card
          styles:
            card:
              - width: 5px
<br>

