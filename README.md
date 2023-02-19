# Digital-Forensics-Project
School lab using Splunk.

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

Before we look at the Splunk app – let’s look at what a packet capture actually looks like. Open a terminal window and type in  

     sudo tcpdump

While tcpdump is running in the terminal, download and install the PCAP Analyzer for Splunk. Notice that tcpdump will give you a summary of the packets it just captured.

Restart your Splunk instance after the installation.

Give rwxrwxrwx permissions to the SplunkForPCAP folder.

Download an example PCAP file to the /home/siem/PCAP/ directory to investigate.

     cd /home/siem/ 
     git clone https://github.com/pat-oconnor/PCAP/ 
     
Log in to Splunk and create a new index called investigations (Settings > Indexes menu.)

Next, Settings > Data Inputs > PCAP File Location

Select New (upper right corner).

In the "Add Data" window, enter WRCCDC in the name field and /home/siem/PCAP/ for the path. 
Check the “More settings” checkbox and set the index to  “investigations”. 
Set your host value to siem.
Click “Next”

The app should start indexing the data within 3 minutes, but this can take a while to complete. The next step will not work until the data has been fully indexed.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Go to the PCAP Analyzer for Splunk app
Under Conversations, add the pcap file to analyze on various screens via “Select tcpdump files”.

In the "Select Statistics", select Conversations by Packets.

Hit Submit.

Check the results below.

