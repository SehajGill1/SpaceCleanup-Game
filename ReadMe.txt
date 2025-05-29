Name: Sehaj Gill
NetID: SSG190004
Date of Submission: 3/28/2025
Computer Platform: Windows 11, AMD Radeon(TM) Graphics
Unity Version: 6000.0.34f1

Description

This project is a space trash cleanup simulation developed in Unity for Assignment 2. The game places the player in control of a spacecraft in orbit around a planet with several moons. The objective is to collect as much space trash as possible before the timer runs out or the player's health reaches zero.

The spacecraft can collide with planetary objects (moons, satellites, planet), collect trash orbiting around the planet and moons, and encounter visual feedback in the form of screen flashes. The player can switch between two cameras for better navigation and visual awareness. UI elements include a score display, a health bar, a timer (with overtime mode), and game over/restart functionality.

Game Features & Controls

-Camera Switching: A UI button at the bottom of the screen toggles between a third-person camera and a rear-view camera.

-Spacecraft Movement: The spacecraft moves forward constantly and the player can control pitch and yaw using mouse or arrow keys. A thrust button increases speed temporarily.

-Trash Collection: The spacecraft collects space trash by colliding with it. Trash disappears and adds to the player score.

-Health System: Colliding with the moon, satellite, or planet reduces player health. When health reaches 0, the game ends.

-Timer: Game starts with a countdown from 60 seconds. When the timer hits 0, the game continues in overtime until trash is collected or health runs out.

-Game Over Conditions:
	-Health reaches 0.
	-All trash has been collected.

UI Elements:
	-Score Text, Health Bar, Timer, Restart Button, Game Over Panel with dynamic messages based on how the game ends

Visual Effects:
	-Red flash on collision
	-Green flash on trash collection

Scripts & What They Do

Core Gameplay:

-SpacecraftController.cs: Handles spacecraft movement, pitch/yaw rotation, and thrust logic.

-SpacecraftCollision.cs: Manages collision logic. Detects when player hits trash or other objects. Reduces health, changes score, spawns trash on moon impact, and triggers visual screen flashes.

-PlayerStatus.cs: Manages player health, score, and handles game over conditions.

-GameTimer.cs: Controls the countdown timer, handles overtime, and detects when all trash is collected.

-GameStartManager.cs: Shows title screen and starts the game when the start button is pressed.

Environment & Objects:

-MoonsOrbit.cs: Makes moons orbit around the planet in circular motion.

-MoonsPlanet.cs: Controls multiple moons orbiting with different speeds and radii.

-MoonsRotation.cs: Rotates moons and planetary trash around their own axis.

-LunarTrashOrbit.cs: Orbits two pieces of trash around each moon at different angles and speeds.

-SatellitesOrbit.cs: Controls movement of two satellites in different orbital planes.

Visual Effects & UI:

-ScreenFlash.cs: Triggers a full-screen red or green flash using a UI Image to indicate hits or trash collection.

-CameraManager.cs: Toggles between third-person and rear-view cameras.

-SpotlightRotation.cs: Rotates the spotlight in front of the spacecraft to simulate scanning.

Challenges & Solutions

-Camera switch not working: Fixed by assigning the correct function to the UI Button's OnClick event.

-Flashes not visible: Solved by ensuring the Image component is enabled and not the whole GameObject.

-Collisions registering multiple times: Added cooldown logic for moon, planet, and satellite collisions.

-No visual feedback on hit/trash: Replaced particles with fullscreen color flashes for clarity.

-Game starting automatically: Used Time.timeScale = 0 and a start button to begin gameplay manually.

-Game Over message not dynamic: Used PlayerStatus and GameTimer to update UI based on how game ended.

Free Assets Used

-NASA Planet Textures: Used for planet, moons, and satellites

-Real Stars Skybox: For background space visuals

-3D Missile Model: Used as spacecraft thrusters for visuals

Video Link

https://youtu.be/VAXZ-luoYsg
