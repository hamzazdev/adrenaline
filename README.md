
# adrenaline
Control your PC's RGB lighting with your smart watch heart rate monitor!

Both color and pulse rate will be impacted. For example, if your heart rate is high, the light will pulse quickly and be a bright red color.

### Implementation details
- We will use the OpenRGB SDK to provide support for the largest number of RGB devices on both Windows and Linux.
- Heart rate should be grabbed every second. The output will be some sort of weighted average with a recency bias.
- Application will have two parts: the watch app, which acts as a client and connects to your PC and sends the heart rate data at 1 hz, and the PC server, which receives the information and updates the RGB devices accordingly.

### How to contribute
Easy! Just open an issue or submit a pull request.
Also, we have a project discord! Here's the link: https://discord.gg/53DUEm

### When will this project be available?
For now, we don't have a timeline, but know we're working on it!

### Further Details
This project so far consits of the fitbit-app which reads hear rate using the sensor API, and sends it over to the companion app. This information is then sent to the nodejs server, which in turn commincates with the openRGB server to change the color of all the RGB components.

## Set Up (Development)
**You will need the following setup/installed:**
	- Fitbit account: https://www.fitbit.com/signup
	- Fitbit Simulator: https://dev.fitbit.com/getting-started/
	- nodejs and npm: https://nodejs.org/en/download/
	- OpenRGB: https://gitlab.com/CalcProgrammer1/OpenRGB#windows

**Step One - Inital Set Up**	
	- Launch OpenRGB (if first time, as admin)
	- Navigate to OpenRGB Server tab and start the server
	- Download/clone this repo
	- Navigate to the server directory in terminal and run
 `npm install` 
	- In the index.js chnage the host IP to the IP of the machine that OpenRGB is running on, if this is the same machine http://localhost will also work
	- Now we will need to run the server, this is done by being inside the server directory and running
	- ` npm start`
	- Now Navigate to the adrenaline-fitbit-app directory in a different terminal window and run
 `npm install`
 	- Open the fitbit simulator -> settings and select Versa 3/Sense as the device type
	- In terminal run
 `npx fitbit` - this will launch the fitbit CLI, on your first launch it will open your browser and prompt you to sign in
	- In the fitbit CLI run
  	- `bi` - this will build the appliction and install it on the simulator
	- In the sensor tab on the simulator, change the heart Rate - there should be change to all the RGB compontents that are detected and compatable with OpenRGB
	- Please open an issue if you have an issue, or join our https://discord.gg/53DUEm and drop a message in the #set-up-issue channel
 