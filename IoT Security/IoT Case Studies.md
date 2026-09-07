# Question 3
The communication is encrypted and the sensor has a valid device ID. Why is encryption alone insufficient to protect this IoT system? Encryption primarily protects the confidentiality of communication and, depending on the protocol, may also provide communication integrity.
However, encryption does not guarantee that the original data itself is truthful. In this scenario, the compromised sensor is generating false data before the data is encrypted.
For example:
• Actual temperature = 80°C
Compromised sensor reports = 40°C
False value is then encrypted and transmitted.
• Encryption protects the communication channel, but it does not necessarily protect the integrity or correctness of the data source.
• Encrypted data ≠ trustworthy data
• A compromised device can generate false data that is perfectly encrypted.
## Solution 3
Encryption secures the transit pipeline, but it cannot validate the honesty of the endpoint producing the payload. Your breakdown captures the core issue perfectly: transport security guarantees confidentiality in transit, not truthfulness at rest or origin.
Encryption alone is not enough in a system of communication as of course we can encrypt the data such temperature etc. There still stands a chance that the data being transmitted has been tampered with completely and the whole file being sent is not right. The whole file could be changed and would still look like encrypted data to the system reading but could be a totally different file as well. 
Encryption ensures that the data is not tampered with as it protects the communication channel, however the entire data file itself could be tamperd with using a Man in the Middle attack. The Attacker can use man-in-the-middle (MITM) to stop the communication altogether and could instead send his/her own data to the device recieving the data. 
And it also doesn't ensure that the device sending the data itself is not compromised. A compromised temperature sensure reporting the wrong data could lead to the data being misread which could be harmful to the device reciving as it can then use those wrong data sets leading to wrong actions. Encryption encodes whatever data the firmware provides. If physical hardware is tampered with, calibrated incorrectly, or compromised via firmware malware, it encrypts the altered payload just as faithfully as accurate data. If compromised firmware is flashed at the factory or pushed during a compromised Over-The-Air (OTA) update, the device will execute bad logic natively behind the encryption layer.

# Question 4
The gateway accepts data because the sensor has a valid identity. Does this necessarily mean that the data is trustworthy?
• A valid device identity proves that the data is associated with an authenticated device, but it does not necessarily prove that the device is behaving correctly or that the data is accurate.
• Thus, Authentication does not automatically imply trustworthiness.
## Solution 4
No, a valid device identity does not mean the data is trustworthy. Authentication proves _who_ sent the message, not _whether_ the sender is operating correctly or reporting the truth. 
Authentication only confirms that the data is being sent by the right device and it's coming from a trustworthy source, however, there is no guarantee that the data coming from the source is trustworthy too. Readings and compromised code and malware all can still persist on a device that is marked as trustworthy. The device is verified by it's unique code, however any code/data/malware on that device that has the trustworthy code might end up being an untrustworthy data. A private key stored in memory remains valid even if the physical sensor element has degraded or the device has been physically tampered with to read incorrent values. If an attacker extracts a private key from one device, they can make infinite number of fake devices all having malicious intents that show up as being trustworthy. 
An authenticated connection acts as a trusted pipe. Once the data is in the pipeline, it can still be affected by a man-in-the-middle attack wherein the data is tampered. 