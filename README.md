# Introduction
As part of the Malware Reverse Engineering course, I was tasked with
analyzing a complex malware sample known as `WebC2-GreenCat-2`.
This report is my own follow-up analysis of the initial analysis my team 
conducted during that time. It provides a detailed examination of the 
malware's capabilities and potential impact, capitalizing on the academic
foundation and practical experienced gained during my time at LSU.

## HTTP Networking:
* I discovered that the malware conducts HTTP networking,
specifically making callbacks to `stratos.macafeepaying.com`.
* This indicated an external command and control (C2) infrastructure
suggesting that the malware's capabilities for receiving instructions
or exfiltrating data remotely.

## Traffic Masquerading:
* It was observed that the malware disguises its network traffic to
mimic Mozilla Firefox web requests, using user agents like
`Mozilla/4.0` or `Mozilla/5.0`.
* This behavior makes it challenging to detect its malicious activities
through standard network monitoring tools.

## Command & Control (C2):
* The malware exhibits C2 behavior, calling back to a designated 
domain for instructions.
* This C2 architecture allows remote operators to control the 
malware adaptively, a critical aspect that I analyzed in-depth 
for its potential threats.

## Reverse Shell Capabilities:
* Features:
	* Commands for file management.
	* Ability to spawn processes.
	* Execution of shell commands under specified user privileges.
* The reverse shell functionality suggests a high degree of control over
an infected system, with a "live-off-the-land" approach to minimize
detection.

## Error Handling:
* Methods:
	* Multitude of tactics for executing essential tasks.
	* Syntax error responses and interactive usage tips.
* This level of sophistication in error handling indicated the
malware's resilience and user-friendliness for the attacker.

## Intended Purpose:
### My analysis points towards the malware's design as an information-stealing 
tool, quietly extracting data while maintaining persistent
access.

# Conclusion
This analysis highlights the sophistication and potential danger
of `WebC2-GreenCat-2` as an information-stealing backdoor. Its ability
to blend in with normal traffic and robust C2 infrastructure,
coupled with a variety of capabilities, underscores its role as a
significant cybersecurity threat. 