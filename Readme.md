#How to run JTrust?

##From Jar:
	>> java -jar jtrust(v1.0) <input_file> <main_class>
	
##Example:
	>> java -jar jtrust(v1.0) in.jtrust Client
	
##Story:
	Let me describe the program context and what we will achieve at the end of the program.
	
	### **Characters:**
		- **Alice** : 
			Alice is the "Patient" - want's to share her medical records to the Doctor for regular health suggestions.
		- **Bob** :
			Bob is the "Doctor" -  suggests medicines as per the patient(s) condition.
		- **Eve** :
			Eve is the "Snooper" - steals information(s) 
		
	### **Technique:**
		- **Declassification** is the mechanism we used for exposing the patient(s) sensitive health record to the open world.
		- **Policy** is used to establish trusted neighbourhood.
		- **Annotation** is used to limit the risk level associated with peer access on the exposed data.
