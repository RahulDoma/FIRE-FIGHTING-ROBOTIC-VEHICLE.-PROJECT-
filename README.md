PROBLEM STATEMENT: 
The security of home, laboratory, office, factory and building 
is important to human life. We develop an intelligent multi 
sensor based security system that contains a fire fighting 
robot in our daily life. 
It is because security system can’t detect abnormal and 
dangerous situation and notify us. 
User may take a late time to extinguish fire like finding the 
water source to extinguish fire when want to extinguish the 
f
 ire.This robot also programmed to stop before the robot hit 
the flames.


ABSTRACT: 
User may take much time to extinguish fire like finding the water  
source to extinguish fire when we want to extinguish the fire. 
This robot will move to the fire source where the flame sensor detects the 
f
 ire and it will send message to any phone of the GSM network through the 
modem connected to the programmable device. 
This robot is equipped with 3 flame sensors where each sensor has its own 
function and commanded control. User may take more time to extinguish fire, like finding 
the water source to extinguish fire when we want to extinguish the fire. 
But few small fire incidents may be hard to detect. 
This Fire Protection Robot design with extinguisher for the intelligent 
building to be controlled by microcontroller PIC18F4550 and supported by 
autonomous board CYTRON SK40C board and another additional circuit.


Code in java:

import java.util.Random;

class FireFightingRobotCar {

    private boolean fireDetected = false;

    // Simulate fire detection sensor with random values
    public boolean detectFire() {
        Random random = new Random();
        // Simulating fire detection randomly
        return random.nextBoolean();  // Fire detected randomly (true/false)
    }

    // Moves robot in different directions
    public void moveForward() {
        System.out.println("Robot is moving forward.");
    }

    public void moveBackward() {
        System.out.println("Robot is moving backward.");
    }

    public void turnLeft() {
        System.out.println("Robot is turning left.");
    }

    public void turnRight() {
        System.out.println("Robot is turning right.");
    }

    // Activates water pump to extinguish fire
    public void activateWaterPump() {
        System.out.println("Water pump activated! Extinguishing fire...");
    }

    // Deactivates water pump when no fire is detected
    public void deactivateWaterPump() {
        System.out.println("Water pump deactivated.");
    }

    // Main control logic for the robot
    public void runRobot() {
        fireDetected = detectFire();

        if (fireDetected) {
            System.out.println("Fire detected! Moving towards fire...");
            moveForward();  // Move towards fire (basic simulation)

            activateWaterPump();  // Activate water pump to extinguish fire
        } else {
            System.out.println("No fire detected. Patrolling...");
            patrol();  // Random movements if no fire is detected

            deactivateWaterPump();
        }
    }

    // Patrol mode when no fire is detected
    public void patrol() {
        Random random = new Random();
        int action = random.nextInt(4);  // Random movement direction

        switch (action) {
            case 0:
                moveForward();
                break;
            case 1:
                moveBackward();
                break;
            case 2:
                turnLeft();
                break;
            case 3:
                turnRight();
                break;
        }
    }

    public static void main(String[] args) {
        FireFightingRobotCar robot = new FireFightingRobotCar();
        
        // Robot runs continuously checking for fire
        while (true) {
            robot.runRobot();

            try {
                Thread.sleep(5000);  // Wait 5 seconds before next action
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
