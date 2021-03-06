# SimplePhilipsHueLib
Simple C# Library to Control Philips Hue

## TestApp
You can get it here: https://github.com/TheCynNrd/SimplePhilipsHueLibTestApp
## Usage

        PhilipsHue HueBridge = new PhilipsHue("YourBridgeIP", "YourUsername");

**Added FindBridge & LinkBridge Function**

       var bridgeip = PhilipsHue.FindBridge(); //automatically detects ip of Bridge
       var username = PhilipsHue.LinkBridge(bridgeip); //waits until you've pressed link button on your bridge.
       //DONT FORGET: save username for later use.
       PhilipsHue HueBridge = new PhilipsHue(bridgeip, username);

**GetRooms**

       //Helpfull if you dont know the Group id, just use this Method to get a List of Rooms with their ID
       var Room = HueBridge.GetRooms(); // Dictionary with IDs
       Room["Diningroom"]; //Will output the ID of Diningroom as example.
        
        

**Turn on Bulp ID 1**

        HueBridge.TurnOn(true,null,null,1);

**Turn on Bulp ID 1 with Color:**    

        HueBridge.TurnOn(true,Color.Red,null,1);

**Turn off Bulp ID 1**

        HueBridge.TurnOn(false,null,null,1);
        
**Turn on Group ID 1:**

        HueBridge.TurnOn(true,null,1,null)

**Turn on Group ID 1 with Color:**

        HueBridge.TurnOn(true,Color.Red,1,null)

**Turn off Group ID 1**

        HueBridge.TurnOn(false,null,1,null)

## Set Color
        
**Change Color of Bulp ID 1**
        
        HueBridge.SetColor(Color.Blue, null,1);

**Change Color of Group ID 1**
        
        HueBridge.SetColor(Color.Blue, 1);

## Effects

**Colorloop on Bulp ID 1**

            HueBridge.Effect("colorloop",null,1);

**Colorloop off Bulp ID 1**

            HueBridge.Effect("none",null,1);

**Colorloop on Group ID 1**

            HueBridge.Effect("colorloop",1,null);

**Colorloop off Group ID 1**

            HueBridge.Effect("none",1,null);

**Alert on Bulp ID 1 with Color**

            HueBridge.Alert("lselect",Color.Red,null,1);
            //Or
            HueBridge.Alert("select",Color.Red,null,1);

**Alert on Group ID 1 with Color**

            HueBridge.Alert("lselect",Color.Red,1,null);
            //Or
            HueBridge.Alert("select",Color.Red,1,null);
