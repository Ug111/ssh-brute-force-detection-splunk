# Splunk SOC Lab: SSH Brute-Force Detection & Alerting

## Objective
This lab simulates SSH brute-force attacks and demonstrates how 
splunk can detect, analyze, and alert on suspicious authentication activity.


## Lab Setup
- Ubuntu (Splunk Server)
- Kali (Attacker)
- Splunk Enterprise installed
- Log Source: /var/log/auth.log

## Data Ingestion
Explain HOW logs entered Splunk
- Monitoring /var/log/auth.log
- Sourcetype used (linux_secure)
- index used (main)
![Splunk Add Data Screenshot](screenshot/add_data_monitor.png)

## Identify Failed SSH Login Attempts
''' index=main "Failed password"

This query searches the ingested authentication logs for all events 
containing the phrase "Failed password", which indicates unsuccessful SSH login attempts

## Observation
The result show multiple failed login attempts across different usernames,source IP adressess,
and timestamps

## Conclusion
This pattern suggests potential brute-force activity, where an attacker is attempting to gain 
unathorized access by trying multiple credentials.

## Identify Top Attacking IP Addresses
''' index=main "Failed password" | stats count by src | sort -count
## Explanation:
- stats count by src aggregates the number of failed login attempts per source IP address
- sort -count orders the results from highest to lowest, highlighting the most active attacker

## Observation:
In this lab, the IP address 127.0.0.1 generated the highest number of failed login attempts (6 attempts)

## Conclusion:
The high frequency of failed attempts from a single IP indicates a concentrated brute-force attack, likely automated
Search in Splunk to confirm events are indexed:
![Ingestion Screenshot](screenshots/search_results.png)

## Step 3: Simulate Failed Logins
Generated failed SSH logins to test alerting:
![Failed Login Event](screenshots/failed_password.png)

## Step 4: Detect Brute-Force Attempts
Query to extract attacker IPs and count failed logins:
![Brute-Force Detection](brute_force_table.png)

## Step 5: Build SOC Dashboard
Visualize failed login trends and top attacker IPS:
![Dashboard Screenshot](screenshots/dashboard.png)

## Summary

This lab demonstrates:
- Hands-on Splunk log injection
- Failed login detection and brute-force identification
- Field extraction and search processing language
- Dashboard creation for SOC visibility

Skills demonstrated: Linux, Splunk, SOC fundamentals, threat detection 
