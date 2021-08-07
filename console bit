input.onButtonPressed(Button.A, function () {
    radio.sendValue("y", 0)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendValue("t", 0)
})
input.onButtonPressed(Button.B, function () {
    radio.sendValue("x", 0)
})
radio.onReceivedValue(function (name, value) {
    if (name.compare("y") == 0) {
        ship.move(-1)
    } else {
        if (name.compare("x") == 0) {
            ship.move(1)
        }
    }
    if (name.compare("t") == 0) {
        shoot = game.createSprite(ship.get(LedSpriteProperty.X), ship.get(LedSpriteProperty.Y))
        shoot.change(LedSpriteProperty.Brightness, 60)
        for (let index = 0; index < 4; index++) {
            shoot.change(LedSpriteProperty.Y, -1)
            basic.pause(15)
        }
        if (shoot.get(LedSpriteProperty.Y) <= 0) {
            shoot.delete()
        }
    }
})
let enemy: game.LedSprite = null
let shoot: game.LedSprite = null
let ship: game.LedSprite = null
ship = game.createSprite(2, 4)
basic.forever(function () {
    enemy = game.createSprite(randint(0, 4), 2)
    enemy.set(LedSpriteProperty.Brightness, 150)
    basic.pause(100)
    enemy.turn(Direction.Right, 90)
    for (let index = 0; index < 4; index++) {
        enemy.move(1)
        basic.pause(500)
        if (enemy.isTouching(ship)) {
            game.gameOver()
        }
    }
    if (enemy.isTouchingEdge()) {
        enemy.delete()
    }
})
