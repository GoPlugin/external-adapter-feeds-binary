# external-adapter-feeds-binary  
Binary for running external adapter and creating teejlab bridges on Plugin nodes  

Prerequisites:  
Active Plugin Node  
Pm2 Process manager  

Steps to use external-adapter-feeds-binary  

Step 1: 
Clone the binary from this repo on to HOME folder where plugin node is runnning.
And provide execute permission.
  
Step 2:  
Create a ".env" file in same folder with below content. Refer Notes below to get more information regarding the parameters CREATE_BRIDGES &  BRIDGE_CREATED  
  
API_KEY=paste_your_api_key  
EA_PORT=XXXX  
CREATE_BRIDGES=true  
BRIDGE_CREATED=false  
BINANCE_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHBNVab  
CRYPTOCOMPARE_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHBrfib  
COINCAP_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHHriab  
COINGECKO_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHBErVb  
COINMARKETCAP_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHBHTib  
COINLAYER_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aTHHVVb  
KUCOIN_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHrfBVb  
TRADERMADE_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHHfTVb  
ZYLALABS_TL_URL=https://goplugin.apidiscovery.teejlab.com/edsn/api/gateway?endpoint_id=aHHEfib  
  
Step 3:  
Paste your teejlab api key to API_KEY variable in .env file
Choose your desired port by setting the variable EA_PORT in .env file

Step 4:
Start the external-adapter-feeds by executing below command  
pm2 start external-adapter-feeds-linux

Step 5:   
Check Plugin UI => Bridges section to confirm all the bridges with correct url to your IP:Port is created  
  
Step 6:  
Use the bridge names to create the jobs.
Bridge names can be reffered from Plugin UI/Bridges section.  
Alternatively, Bridge names and Url will be written to a file where the binary is executed => ExternalAdapterData.txt  

Notes:  
More information on usage of parameter CREATE_BRIDGES & BRIDGE_CREATED  
You do not have to modify the CREATE_BRIDGES & BRIDGE_CREATED variables in .env file, It will be automatically taken care by the binary.    
  
In case you want to modify then here goes the required details to know before modifying   
CREATE_BRIDGES = true, BRIDGE_CREATED= false => This will create bridges, and start External Adapter, Use this configuration when you run the ExternalAdapter binary first time.  
CREATE_BRIDGES = false, BRIDGE_CREATED= true => This will not create new bridges, and start External Adapter. Use this configuration for subsequent restarts.  




