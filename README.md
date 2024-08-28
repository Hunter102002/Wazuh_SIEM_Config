# Wazuh SIEM Configuaration

## Objective

Set up Wazuh to monitor multiple machines (Windows and Kali Linux) by connecting agents, testing log collection, and using Nmap and Hydra to simulate attacks for log analysis.

### Skills Learned

- Agent Deployment: Successfully installed and configured Wazuh agents on multiple machines (Windows and Kali Linux).
- Log Collection and Monitoring: Set up Wazuh to collect and monitor logs from different sources, including system logs and security events.
- Attack Simulation: Used tools like Nmap and Hydra to simulate network scans and brute-force attacks, analyzing how these activities are logged in Wazuh.
- Log Analysis: Reviewed and interpreted the logs generated from simulated attacks to assess the effectiveness of the Wazuh setup in detecting and alerting on suspicious activities.

### Tools Used

- Wazuh: For centralized monitoring and log analysis of connected machines.
- Nmap: To perform network scans, identifying open ports and services on the monitored machines.
- Hydra: To simulate brute-force attacks on the monitored machines, testing Wazuh's ability to detect and log these activities.
- Windows/Linux VMs: Target machines where Wazuh agents were installed and monitored for suspicious activities.

### Outcome
This project successfully demonstrated the deployment and configuration of Wazuh agents on multiple machines and the ability to monitor and analyze logs in a centralized Wazuh dashboard. By using Nmap and Hydra to simulate network scans and brute-force attacks, the project tested Wazuh's effectiveness in logging and alerting on potentially malicious activities. The project highlighted skills in agent deployment, log collection, and security event monitoring, providing a comprehensive understanding of how to use Wazuh for security operations.
                                 
## Steps

After configuring wazuh on a host server, log into the dashboard and click 'add agent.' from there, configure the machine settings and copy and paste the prompt into your machines 

![Screenshot 2024-08-26 220739](https://github.com/user-attachments/assets/360d5c7b-415e-45ed-aad1-e8bd33e11333)

![Screenshot 2024-08-26 221025](https://github.com/user-attachments/assets/18defb75-a2a3-462b-a00e-f509ca9adee2)

![Screenshot 2024-08-27 120437](https://github.com/user-attachments/assets/00e095bf-9609-42db-9870-be5b8cc43677)

![Screenshot 2024-08-27 163034](https://github.com/user-attachments/assets/63c990cd-97ed-4652-a623-45b08282052d)

--------------------------------------------------------------------------------------------------

We can run an Nmap scan on one of the machines to gain information on open ports, which we can test 

![Screenshot 2024-08-27 173027](https://github.com/user-attachments/assets/45a67619-a531-4b47-8486-f10547b06b91)

--------------------------------------------------------------------------------------------------

Now run a hydra attack on the machine to test the log config in Wazuh 

![Screenshot 2024-08-27 173052](https://github.com/user-attachments/assets/20607226-a94e-47c7-8a37-1d0098a27a7e)

--------------------------------------------------------------------------------------------------

Analyze the logs, we can see that an alert for multiple failed sign-in attempts shows up, which is a level 10 threat; through further investigation, the log says this is a brute force attack, which would be correct 

![Screenshot 2024-08-27 174738](https://github.com/user-attachments/assets/c6d80fbb-35ff-4e5d-b173-d4dc369c64ce)

![Screenshot 2024-08-27 174838](https://github.com/user-attachments/assets/19247c0d-5158-4086-a0dd-13afdf3679ad)

--------------------------------------------------------------------------------------------------

Now we know our SIEM is working, and from here, we can go through important analyses that Wazuh gives us; the main dashboard will give us a compliance dashboard, which we can filter to show us our compliance status to the common compliance statutes. It also gives us a SCA scan, which we can use to harden our machines, making it less vulnerable to attacks, as well the MITRE framework attacks, which our machine may be vulnerable to

![Screenshot 2024-08-27 175331](https://github.com/user-attachments/assets/7b5c0e9a-9174-4486-94f3-0ba04cb776c1)

--------------------------------------------------------------------------------------------------

Glancing at the security events, we can see many T1078 types of attacks. This is an initial access attack and was triggered by our Hydra attacks; the log also gives us a quick summary of the attack type and some notes.

![Screenshot 2024-08-27 180406](https://github.com/user-attachments/assets/158cff1b-1e6f-4b97-94e1-9bdd5f93dfc4)

![Screenshot 2024-08-27 180426](https://github.com/user-attachments/assets/437dc23a-4e8a-45e3-b580-d3adbe479caa)

------------------------------------------------------------------------------------------------

Wazuh also does a security benchmark scan which we can use to harden our machines, we can see my machine now is at 32% and it tells me the places I failed and gives me tips on how I can fix it, and harden my machine 

![Screenshot 2024-08-27 180456](https://github.com/user-attachments/assets/ec75cae9-0365-4d5b-8940-b89c8aa1f2f3)

![Screenshot 2024-08-27 180512](https://github.com/user-attachments/assets/08beef3f-544b-466e-b5c4-bfdbf8d1b004)

--------------------------------------------------------------------------------------------------













