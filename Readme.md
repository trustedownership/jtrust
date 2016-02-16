#How to run JTrust?

##From Jar:
	>> java -jar jtrust(v1.0) <input_file> <main_class>
	
##Example:
	>> java -jar jtrust(v1.0) in.jtrust Client
	
##Story:
	Let me describe the program context and what we will achieve at the end of the program.
	
	> Characters:
	  -----------
		- Alice : 
			Alice is the "Patient" - want's to share her medical records to the Doctor for regular health suggestions.
		- Bob :
			Bob is the "Doctor" -  suggests medicines as per the patient(s) condition.
		- Eve :
			Eve is the "Snooper" - steals information(s) 
		
	> Technique:
	  ----------
		- Declassification is the mechanism we used for exposing the patient(s) sensitive health record to the open world.
		- Policy is used to establish trusted neighbourhood.
		- Annotation is used to limit the risk level associated with peer access on the exposed data.
		
	> Screen Play:
	  ------------
		- Alice wants to expose her private, sensitive medical record (mRecord) to the open world for some good purpose.
		- While exposing her data, Alice is following the policy(alpha) (line 86,87).
		- Now, the data is in open world (line 93).
		- As per policy(alpha), none can access Alice's 'mRecord' data, since she didn't declare anyone in her trusted neighbourhood.
		- However, Bob wants her data for medical processing.
		- To enable permission for Bob, Alice is modifying her policy from 'alpha' to 'beta' (line 102).
		- Now, Bob can 'read', however cannot 'modify' as per 'policy(beta)'.
		- Sometime, Bob additionally require modify permission in order to update her record in certain cases, like prescribing prescription etc,.
		- If Alice likes to enable 'modify' permission to Bob, she can change her policy to 'gamma' (line 106,107).
		- Now, after modifying the policy level to 'gamma', Bob can modify.
		- However, Eve (the snooper), cannot access (read/modify) Alice's private, sensitive information shared to Bob in the open world.
		- The End.