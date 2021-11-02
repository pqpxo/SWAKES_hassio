# Mobile Light Dashboard

Here’s a quick breakdown of the dashboard …

Essentially the dashboard has been created using a ton of ‘**custom:button-card**’, ‘**custom:state-switch**’ cards and various ‘**input_selects**’.

The ‘**custom:button-card**’ are used in nearly everything when it comes to the buttons, titles, labels etc. I tend to use them a lot due to them being super customizable. The ‘**custom:state-switch**’ element is used as a card to show a predefined set of cards/elements depending on an entities state. Finally, the ‘**input_selects**’ are created with the options reflecting the desired menu options on the dashboard.

In this example (below), I’ve created an ‘**input_selects**’ for each of the floors in my house, also including ‘Overview’ for a single, ‘front page’ overview of each dashboard type.

```
input_select:
  light_menu_select:
    name: 'Light Menu Select'
    options:
      - Overview
      - Ground
      - First
      - Second
    initial: Overview
    icon: mdi:home

```

I’ve used this combination of ‘**custom:state-switch**’ and ‘**input_select**’ elements throughout this dashboard to create a sort of ‘makeshift’ menu selector function to display stuff a bit more streamline in HA.

Anywho, into the nitty gritty stuff, the card basically consists of three parts which are all housed within a ‘vertical-stack’ card …

-   ![#FF0000](https://via.placeholder.com/15/FF0000/000000?text=+) **Header** \- You’ve guessed it. It’s the header for this dashboard and simple shows the title, icon and label, which changes to menu options selected below (In this case ‘Overview’ should be ‘Ground’ in the image below). Created with a single ‘custom:button-card’ whilst using the ‘grid’ option to define the cards layout
    
-  ![#c5f015](https://via.placeholder.com/15/FFFF00/000000?text=+)  **Menu** \- Another ‘**custom:button-card**’ but this time including an ‘**input\_select**’ into the mix which will set a predetermined state for the ‘**input\_select**’ entity when pressed.
    
-  ![#1589F0](https://via.placeholder.com/15/00FF00/000000?text=+)  **Content** \- This is where the magic happens. Depending on the button pressed above and thus changing the ‘**input_select**’ state, we can use the ‘**custom:state-switch**’ to only display set bunch of stuff depending on the state.
    

![enter image description here](https://i.imgur.com/aRB10pG.jpg)

### **Components required**

-   ‘**[custom:button-card](https://github.com/custom-cards/button-card)**’ \- Create buttons, labels/titles, card
-   ‘**[custom:state-switch](https://github.com/thomasloven/lovelace-state-switch)**’ \- Display certain cards
-   ‘**[custom:card-mod](https://github.com/thomasloven/lovelace-card-mod)**’ \- Required for styles, theming of cards
-   ‘**[custom-brand-icons](https://github.com/elax46/custom-brand-icons)**’ \- Optional, use ‘mdi’ icons instead
-   ‘**[input_select](https://www.home-assistant.io/integrations/input_select/)**’ \- Required for selecting menu, option

## Header

This ‘**Header**’ card is comprised of a ‘**custom:button-card**’ to show the title, icon and menu option selected as the label. To get the desired layout, I’ve used the ‘[grid](https://github.com/custom-cards/button-card#custom-fields)’ option to set each element in place. I’d highly recommend using [this site](https://grid.layoutit.com/) when attempting to create a ‘**custom:button-card**’ with a ‘grid’ as it’ll definately help.

As you can see below, in order to show the corrisponding menu option title in the header (underneath ‘LIGHTS’), a ‘return states…’ statement in used pointing at the ‘**input_select**’ in question (`input_select.light_menu_select`).

Before we delve in further, it’s worth mentioning that most, if not all of the cards and elements in this dashboard are modified (in terms of styling) to cater my personal devices. This means that certain bits such as font size, spacing and other styling elements may look different and would need tweaking to suite your setup (screen size, resolution).

Here is the example config below …

```
type: custom:button-card
name: LIGHTS
icon: phu:bulb-group
show_state: false
label: |
  [[[
    return states['input_select.light_menu_select'].state;
  ]]]
show_label: true
styles:
  card:
    - height: 80px
    - background-color: transparent
  grid:
    - grid-template-areas: '"i n" "i n" "i l"'
    - grid-template-columns: 0.3fr 1fr
    - grid-template-rows: min-content min-content min-content
  img_cell:
    - align-self: start
    - text-align: start
  name:
    - justify-self: start
    - font-size: 28px
    - font-weight: 300
  label:
    - justify-self: start
    - font-size: 16px
    - font-weight: 300
  icon:
    - width: 45px
    - align-self: start
    - text-align: start

```

## Menu

Same as before, another use of the ‘**custom:button-card**’ however several lined up within a ‘**horizontal-stack**’. Nothing fancy with this card setup apart from the additional ‘**tap\_action**’ element at the bottom which will select the floor in question. The use of ‘**state**’ is used to apply a opacity/transparency to the card when it’s not been selected and highlighted otherwise. It’s key that the relevant ‘**input\_select**’ and ‘value’ are replaced for each card in order for this work.

This example is for the ‘Ground’ button/menu option …

```
type: custom:button-card
color: transparent
entity: input_select.light_menu_select
show_name: true
color_type: label-card
name: Ground
icon: mdi:home-floor-g
state:
  - icon: mdi:home-floor-g
    styles:
      icon:
        - color: white
        - width: 40px
      name:
        - color: white
        - font-size: 12px
        - padding-top: 5px
    value: Ground
  - icon: mdi:home-floor-g
    styles:
      icon:
        - color: white
        - opacity: 0.5
        - width: 40px
      name:
        - color: white
        - font-size: 12px
        - padding-top: 5px
    operator: default
tap_action:
  action: call-service
  service: input_select.select_option
  service_data:
    entity_id: input_select.chr_light_menu_select
    option: Ground

```

## Content
Now we've sorted out the Header and Menu parts/mechanism, it's time to display some stuff. Here is where the '**custom:state-switch**' comes into action. As a quick reminder, the '**custom:state-switch**' card will display a certain set of cards/elements depending on the state of an entity. To get the ball rolling, simple create a new card starting with the following code (using your own '**input_select**' entity and options) ...

    type: custom:state-switch
    entity: input_select.chr_light_menu_select
    states:
      Overview:
        type: vertical-stack
        cards:
           ....
      Ground:
        type: horizontal-stack
        cards:                  
            - type: custom:button-card
              icon: phu:table-shade
              show_icon: false
              ...

  
Underneath '**states:**' you need to include the options from your 'input_select' (in my case Overview, Ground ...) and then the content below. This means that when, for example, 'Ground' is set (by clicking on the Menu button above) it will only display the content listed under, you guessed it, the Ground state.

This can get a tad bit messy as essentially you're creating cards within cards so I would highly recommend building each bit of content/elements in a seperate card/dashboard and once completed, add them into the '**custom:state-switch**' at the end. It's also handy to keep those seperate cards incase you need to edit/amend anything at a later date!

Now we've covered the three main parts you're set to make your own desired dashboard! However if you're interested in the content I managed to conjure up, let's ramble on some more ...

## More Content
Before we begin, let me give some context into my content cards. As this is my Lights dashboard, I've broken down and grouped my lights into certain floors within my house. I've then further created two sections under each floor, one for Lights and another for automations. 

![enter image description here](https://i.imgur.com/2F9m8Pb.jpg)

To create a card/box for each room would of taken up too much space so I've used the magic as mentioned above and again created an 'input_select' and '**custom:state-switch**' element. This is all done within a single '**custom:button-card**' using the 'grid' option. 

Before we get into the '**custom:button-card**' bit, you'll need to create another '**input_select**' entity for this part. In my example, I've created a new entity to cover each room like so ...

    input_select:
      light_room_select_ground:
        name: 'Lights Ground Room Select'
        options:
          - Hallway
          - Snug
          - Kitchen
        initial: Hallway
        icon: mdi:home-floor-g  

Now back to the card business, to do this I've created a grid with 4 columns and 2 rows and created the 'grid-template-areas' as '**ln**', '**r1**', '**r2**', **r3**' and '**rm**'.

 - '**ln**' is the label/name for the selected room
 - '**r1**' is the icon for the first room (Hallway in the case)
 - '**r2**' is for the second room (Snug)
 - '**r3**' is for the third room (Kitchen)
 - '**rm**' is the area below the top row to display the content    
 

![enter image description here](https://i.imgur.com/JfJcjrB.jpg)
![enter image description here](https://i.imgur.com/6RR15XP.jpg)

      - type: custom:button-card
        icon: phu:table-shade
        ...
        ...
        ...
        styles:
           ...
           ...
          grid:
            - grid-template-areas: '"ln r1 r2 r3" "rm rm rm rm"'
            - grid-template-columns: 55% 15% 15% 15%
            - grid-template-rows: min-content 1fr
            - gap: 15px 1px

Above is the code I've used to conjure up this madness. As mentioned way back above somewhere, when it comes to sizing/formatting, I've used the following values (`55% 15% 15% 15%` and `min-content 1fr`) to suit my display needs and may need amending for your setup. 

It's worth noting that if you need more than 3 options (r1, r2, r3), simply create another (r4) and adjust/include an additional value under `grid-template-columns`and `grid-template-areas`like so ...

    - grid-template-areas: '"ln r1 r2 r3 r4" "rm rm rm rm rm"'
    - grid-template-columns: 40% 15% 15% 15% 15%  

Now we've got the grid part sorted, we can begin the adding stuff in part. Yey. Firstly we need to sort out the top row where the label/name and buttons live. Next to add is the `custom_fields:` part and underneath, each `grid-template-area`which the content below. 

Here is an example of the card so far with `r1` and `ln`. To save on screen space I've skipped `r2` and `r3` as they are essentially the same as `r1` but with different values (remember to change the icon, value and option values for each one).

    type: custom:button-card
    icon: phu:table-shade
    ...
    ...
    styles:
      ...
      ...
      grid:
        - grid-template-areas: '"ln r1 r2 r3" "rm rm rm rm"'
        - grid-template-columns: 55% 15% 15% 15%
        - grid-template-rows: min-content 1fr
        - gap: 15px 1px
    custom_fields:
      r1:
        card:
          type: custom:button-card
          entity: input_select.light_room_select_ground
          name: false
          show_name: false
          aspect_ratio: 1/1
          state:
            - icon: phu:rooms-staircase
              styles:
                card:
                  - background-color: '#242e42'
                icon:
                  - color: white
                  - width: 25px
              value: Hallway
            - icon: phu:rooms-staircase
              styles:
                card: null
                icon:
                  - color: white
                  - width: 25px
                  - opacity: 0.6
              operator: default
          styles:
            icon: null
          tap_action:
            action: call-service
            service: input_select.select_option
            service_data:
              entity_id: input_select.light_room_select_ground
              option: Hallway
      r2:
        card:
          type: custom:button-card
          ...
          ...
      r3:
        card:
          type: custom:button-card
          ...
          ...          
      ln:
        card:
          type: custom:button-card
          color: transparent
          name: |
            [[[
              return states['input_select.light_room_select_ground'].state;
            ]]]
          styles:
            card:
              - background-color: transparent
            name:
              - font-size: 18px
              - font-weight: 300
              - justify-self: left
              - padding-left: 2%
              - padding-top: 3%
              - padding-bottom: 3%

So now we've managed to create the top row and selection buttons (using the `tap_action` > `call-service` > `input_select.select_option` > `option`), it's time to display the relevant content. To do this we use our good old friend '**custom:state-switch**' again underneath the rm to like so ...

    type: custom:button-card
    icon: phu:table-shade
    ...
    ...
    custom_fields:
      r1:
        card:
          type: custom:button-card
          ...
          ...
      r2:
        card:
          type: custom:button-card
          ...
          ...
      r3:
        card:
          type: custom:button-card
          ...
          ...      
      ln:
        card:
          type: custom:button-card
          ...
          ...
      rm:
        card:
          type: custom:state-switch
          entity: input_select.light_room_select_ground
          states:
            Hallway:      
              type: vertical-stack
              cards:        
                ...
                ...
            Snug:      
              type: vertical-stack
              cards:        
                ...
                ...            
            Kitchen:      
              type: vertical-stack
              cards:        
                ...
                ...            

And that's it! Hopefully you've been able to follow my ramblings and make some sort of sense! 

You'll be able to find the full YAML code and examples within this folder in GitHub.

This whole process/setup took me a fair few weeks to create so if you spot any errors or 'better ways of working' (thinking of **custom:button-card** templates maybe), please let me know by dropping me a message on **Reddit**, **Facebook** or the **Home Assistant Community forum**.

Also I've you've enjoyed this guide and want to show your appreciation some how, please [Buy Me A Coffee here](https://www.buymeacoffee.com/swakes)!


    
-   Reddit - [https://old.reddit.com/user/swake88/submitted/](https://old.reddit.com/user/swake88/submitted/)
    
-   Blog - [https://hmas.swakes.co.uk](https://hmas.swakes.co.uk/?fbclid=IwAR2C_NhUkD9BoStN323iteVV36vM665RzfQYAS8BplibtuTl-dT28h2thPM)
    
-   Pastebin - [https://pastebin.com/u/pqpxoxa](https://pastebin.com/u/pqpxoxa?fbclid=IwAR38cCRP1sUIKekn6e8RAer11AkLDKm-eTOGOLhQGK5ieFWaaFDZ6g1QdEw)
    
-   BMAC - [https://www.buymeacoffee.com/swakes](https://www.buymeacoffee.com/swakes?fbclid=IwAR2C0bO2Ag_xclFUWKKHTU2TTmgFTnfBex8O8tJrV8YUXCcnp-LrGLUPgfY)
- HA Community - https://community.home-assistant.io/u/pqpxd
