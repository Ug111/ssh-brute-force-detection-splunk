# SOC Readiness Lab with Splunk

This repository documents a hands-on Skills demonstrated:
- Log ingestion and monitoring
- Failed login detection
- Brute-force attack analysis
- Dashboard creation and alerts
- 

## Prerequisities
- Ubuntu 20.04+ machine
- Splunk Enterprise installed
- Basic Linux command line knowledge

## Step 1: Monitor System Logs
Monitored files '/varlog/syslog' and '/var/log/auth.log'
![Add Data Screenshot](screenshot/add_data_monitor.png)

## Step 2: Verify Data Ingestion
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
