# ec-helm-plugin-testing
## Usage for EC-Helm E2E Microservices testing :  

1. Do initial deploy without additional options  
2. Do upgrade deploy with changed settings via additional options.  
What can be controlled described in controls.  

#### Negatives :   
1. Use wrong image.tag to fail promotion  
2. Use not existing option to fail helm install  


## Charts and other testing data  

#### blue_green  
	BlueGreen strategy  
	controls :   
		image.tag=0,1 or 0,2  
		promotion.auto=true or false  
		promotion.seconds=~ or number in seconds  
		
#### canary_multi_pause  
	Canary with multiple pauses. Indefinite and several timed  
	controls :  
		image.tag=blue or green  
		
#### canary_pause  
	Canary with pause.  
	controls :  
		image.tag=0,1 or 0,2  
		pause.duration=~ or number in seconds  
		
#### canary_pause_with_steps  
	Canary with indefinite pause and weight set to 30  
	controls :  
		image.tag=0,1 or 0,2
        pause.duration=~ or number in seconds