# Digital-Forensics-Project
This project was done during our Flatiron School bootcamp.

Abstract: The goal of this lab is to understand how digital evidence is obtained, cataloged and the incident response started in a virtual environment.  

In this lab, we will be running PCAP Analysis for Splunk. Pcap files are network packet captures. Splunk will ingest these files so you can do an analysis on them. 

The data provided for this lab came from the Western Regional Collegiate Cyber Defense Competition in February of 2019. 

Procedure – Detailed Lab Steps
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Log in to the SIEM vm.

Make sure the splunk home settings are correct.
     
     export SPLUNK_HOME=”/opt/splunk”
     
Edit the /etc/environment file

     sudo nano /etc/environment
     
Make sure the second line of the file says, SPLUNK_HOME=”/opt/splunk”

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Install tshark

     sudo apt-get update
     sudo apt install tshark -y
Allow non-superusers to capture packets
