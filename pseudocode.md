# Pseudocode for a Claw Machine

## **Task**: When the user inserts a coin into the claw machine, start the game and let the user move the crane depending on the joystick position. Then when the user presses the button on the cabinet, make the crane move down and close.

<br></br>
### Extra Info

- the `stick` object gets its position from the physical joystick
- the `button` object gets its state from the physical button
- the `coinMech` object gets its state from the physical coin mechinism
- the `crane`'s position (x,y,z) cannot go past physical limitations

<br></br>


### Define Objects

1. `stick`
    - positionX: represents the joystick's left and right position
    - positionY: represents the joystick's up and down position

2. `button`
    - state: represents the state of the button, either 'pushed' or 'notPushed'

3. `coinMech`
    - state: represents the state of the coin mechanic, either 'coinAccepted' or 'coinRequired'

4. `crane`
    - positionX: represents the crane's left right position
    - positionY: represents the crane's forward backward position
    - positionZ: represents the crane's up down position

5. `claw`
    - state: represents the state of the claw, either 'open' or 'closed'

6. `prizeExit`
    - positionX: represents the left right position of the prize exit
    - positionY: represents the forwards backwards position of the prize exit

### Define Functions

- `gameStart`: where the program preforms the game functions
- `stickInput`: where the program checks the position of the joystick and moves the crane

<br></br>

### Pseudocode Objects and Functions

``` 
START

wait until coinMech.state is coinAccepted
gameStart

function gameStart
    while button.state is notPushed
        run stickInput
    set claw.state to open
    lower crane.positionZ
    set claw.state to close
    raise crane.positionZ
    move crane.positionX to pizeExit.positionX
    move crane.positionY to prizeExit.positionY
    set claw.state to open

function stickInput
    if stick.positionX is left move crane.positionX left
    if stick.positionX is right move crane.positionX right
    if stick.positionY is up move crane.positionY forward
    if stick.positionY is down move crane.positionY backward

END
```
