
# Yet Another Mobile Dashboard Redesign

### Title / Header Card

<p>
  <img src="https://raw.githubusercontent.com/pqpxo/SWAKES_hassio/refs/heads/master/guides/Yet%20Another%20Mobile%20Dashboard%20Redesign/Images/titleheader.png" />
</p>

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



