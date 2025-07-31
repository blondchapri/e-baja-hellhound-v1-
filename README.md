# hellhound-v1
an archive of the thoughts , ideas and thought processes in designing a thought experimental electric baja buggy meant for research and learning of designing a ebaja buggy

## For this thought experimental e BAJA buggy I have set my target parameters as : 
-	fully follow the rules laid down by SEA India for the BAJA season 2026 
-	90% Gradeability
-	at least hit 60km/h
-	using as much inventory of team Pegasus baja as possible 
## Power train :
to hit the 90% Gradeability I will use 4 x motors :
- 2 x Yalu Brushless DC Motor 3000W for the rear wheels, one motor on each
- 2 x Yalu Brushless DC Motor 1500W for the front wheels, one motor on each <br>
y 4 motors ? cuz ambani mere lode pe <br>
this gives us total torque of the 4 x motor = 27nm , which is way to low for our application of off road sporting  <br>

and then I did math stuff and figured this shit is stupid, too complex, better to use a single good motor rather than 4 shitty ones, so I switch to 
**1x DATAI PMSM Motor 8000W 60V/72V dual speed**
it has **50nm of torque** ( ˶°ㅁ°) !! <br>

did more math stuff and got to the conclusion that a static gear box was not very versatile and bad , then I remembered Team Pegasus Baja’s inventory has a CVT and would be perfect for this and would help in making the static gearbox smaller while giving good torque and maintaining nice sustained/top speeds , the one we had was an old **Gaged GX9** 
again did math stuff landed on the gear ratio of **3:1** for the static gear box , with GX9 the total ratio comes out to **11.7:1** this keeps the gradability at 90% assuming weight is 270kg and using the existing wheels used by Team Pegasus baja in the size of **23X7-10**
for the battery we will go with 80ah cuz 80 is the highest we can use (-_-)
maybe 2x 40ah ones or 4x 20ah 
## electrical layout
did research and landed on this setup for main tractive system 
<img width="940" height="336" alt="image" src="https://github.com/user-attachments/assets/3579a708-bb26-453c-a7d1-e1a255276a1e" /> <br>
then cross checked from the rule book and found a rule stating LV components need separate auxiliary battery then finally landed on this 
<img width="940" height="431" alt="image" src="https://github.com/user-attachments/assets/c27eac72-8f5f-40de-9004-cf0bc6a38176" /> <br>
## THE VALUES of components till now 
-battery: main tractive system battery rated at 72v 80ah
-Bms: a smart automotive BMS that triggers preload/recharge circuit, contactor with Overvoltage, Under Voltage, overcurrent protection and short circuit protection at every cell
-Fuse :125 amps
-Contactor: rated at 125 amps and coil voltage preferred to be 12, online price dekh ke gand phat gaya but I think locally should be cheaper as it is regularly used in -----industrial automation 
-auxiliary battery: will depend on other LV components, will try to keep all nominal voltages of LV components the same as stepping it down or up is not allowed for category 2 as category 2 now is mandatory 
-kill switch: push to open rotary switch like the one used in mega atv  
<img width="123" height="123" alt="image" src="https://github.com/user-attachments/assets/b29689a8-e55a-4b63-9823-5bc02c18b8fe" />
-RTDS circuit: all the components will be rated at the battery’s nominal voltage , or the controler will have a seprate power source, the controller gets a input when we energise the kill switch and it closes the circuit on the relay/transistor which completes the circuit of the buzzer , or on the other hand if I can find a strong enough buzzer that zero can drive with the gpio I will use that
<img width="940" height="179" alt="image" src="https://github.com/user-attachments/assets/de7df1ec-6f98-493f-bdc5-3d3b3ede1f6c" /> <br>
-Motor controller: will try to buy in a bundle with motor as the default one will be optimized for the motor 
-throttle: a premade hall effect one 
-Pre-charge resistor: depends on the motor controller 
-icrocontroller: heavily leaning towards RP2040zero 
## the gear box 
I was thinking a **planetary gearbox** with the ratio of 3:1 that sits on the motor and then outputs to GX9 and GX9’s secondary is connected to the cv shafts , but I think we should add a differential so the turns will be PURE CINIMA but ig it will be too complex and transmission team wale meri gand mardenge cuz differential bhi limited slip he chiye agar dalenge toh :)
my reasoning behind a planetary gearbox <br>
<img width="940" height="978" alt="image" src="https://github.com/user-attachments/assets/fe366844-cbbd-4580-ac27-1337efbb27b2" />
my reasoning behind a LSD <br>
<img width="940" height="492" alt="image" src="https://github.com/user-attachments/assets/6484c510-af0a-40db-ad0d-b294ee7bc4d0" />


