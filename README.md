# IoT3D
This project focus to concentrate various different ESP projects in one consistent line of "Ready to Use" sensors for Home Assistant.

Every sensor is 3D printed and shipped with a Tasmota custom firmware, Ready to Use.
Additionally, there's a section containing all the different configurations for ESPHome to help end user to compile his custom firmware on his own.
There's a file for every sensor model, at the begin of every file there are variable declaration where you have to modify data to adapt to your network/use case

# ESPHome Installation - Ultrasonic Sensor
First of all we have to customize the code:

`https://stackoverflow.com/a/62362724 function bytesArrToBase64(arr) { const abc = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"; // base64 alphabet const bin = n => n.toString(2).padStart(8,0); // convert num to 8-bit binary string const l = arr.length let result = ''; for(let i=0; i<=(l-1)/3; i++) { let c1 = i*3+1>=l; // case when "=" is on end let c2 = i*3+2>=l; // case when "=" is on end let chunk = bin(arr[3*i]) + bin(c1? 0:arr[3*i+1]) + bin(c2? 0:arr[3*i+2]); let r = chunk.match(/.{1,6}/g).map((x,j)=> j==3&&c2 ? '=' :(j==2&&c1 ? '=':abc[+('0b'+x)])); result += r.join(''); } return result; } let array = new Uint8Array(32); window.crypto.getRandomValues(array); document.getElementById("api-key").value = bytesArrToBase64(array); `
