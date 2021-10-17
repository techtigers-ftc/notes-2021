# Sample Mock

This is a code sample that shows unit testing with mocks.


```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware.Gamepad;

import static org.mockito.Mockito.*;
import org.junit.jupiter.api.*;


import static org.junit.jupiter.api.Assertions.*;

/**
 * This is a dummy class created to demonstrate testing using mockito
 */
class Controller {
    // This property will get mocked using mockito
    private Gamepad gamepad;

    /**
     * Creates a new controller instance, and accepts a gamepad object from which inputs will be
     * read.
     *
     * @param gamepad The gamepad that provides user inputs
     */
    public Controller(Gamepad gamepad){
        this.gamepad = gamepad;
    }

    /**
     * Returns the direction for the robot to go based on controller inputs
     * @return Te direction for the robot
     */
    public double getDirection() {
        double direction = 0;

        // Checks if dpad down is pressed and sets direction
        if (this.gamepad.dpad_down){
            direction = 180;
        }

        // Checks if dpad left is pressed and sets direction
        if (this.gamepad.dpad_left){
            direction = -90;
        }

        // Checks if dpad right is pressed and sets direction
        if (this.gamepad.dpad_right){
            direction = 90;
        }

        return direction;
    }
}

/**
 * Tests for the Controller class by using mockito
 */
public class SampleTest {
    // Mock Gamepad object used to mock a user input
    private Gamepad mockGamepad;

    /**
     * Initializes our Controller object with a mock gamepad
     * @return The controller object
     */
    private Controller initController() {
        this.mockGamepad = mock(Gamepad.class);
        Controller controller = new Controller(this.mockGamepad);
        return controller;
    }

    @Test()
    public void testDriveBack() {
        Controller controller = this.initController();

        // Set the dpad down to true, and expect the robot to drive backward.
        this.mockGamepad.dpad_down = true;
        assertEquals(controller.getDirection(), 180);
    }

    @Test()
    public void driveFront() {
        Controller controller = this.initController();

        // Set the dpad up to true, and expect the robot to drive forward.
        this.mockGamepad.dpad_up = true;

        assertEquals(controller.getDirection(), 0);
    }

    @Test()
    public void driveLeft() {
        Controller controller = this.initController();

        // Set the dpad left to true, and expect the robot to drive left.
        this.mockGamepad.dpad_left = true;

        assertEquals(controller.getDirection(), -90);
    }

    @Test()
    public void driveRight() {
        Controller controller = this.initController();

        // Set the dpad right to true, and expect the robot to drive right.
        this.mockGamepad.dpad_right = true;

        assertEquals(controller.getDirection(), 90);
    }
}
```
