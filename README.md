# Pong 2D Game
# About: 2D Pong game for desktop use, made using libGDX, Java
![Screenshot](https://i.ibb.co/JRy6Cp2/Screen-Shot-2021-06-21-at-11-02-26-AM.png)

# Details: 
Left side: we have computer player\
Right side: user player\
Controls: W to go up, S to go down
# Note:
Ball speed increase by time and it becomes hard to dodge.\
Ball directon is random.\
There are walls on top and bottom.

# Computer player logic:

``` Java
public class PlayerAI extends PlayerPaddle {

    public PlayerAI(float x, float y, GameScreen gameScreen) {
        super(x, y, gameScreen);
    }

    @Override
    public void update() {
        super.update();

        Ball ball = gameScreen.getBall();
        if (ball.getY() + 10 > y && ball.getY() - 10 > y)
            velY = 1;
        if (ball.getY() + 10 < y && ball.getY() - 10 < y)
            velY = -1;

        body.setLinearVelocity(0, velY * speed);
    }
}
end
```
