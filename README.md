# CloudWatch Monitoring Using AWS EC2

Hosted monitoring and alerting for an EC2 instance using AWS CloudWatch alarms.

## Project Overview

This project demonstrates how to monitor an EC2 instance using AWS CloudWatch.

The project includes:

* Monitoring CPU Utilization
* Creating CloudWatch Alarms
* Configuring SNS Email Notifications
* Triggering CPU spikes manually
* Observing alarm state changes from OK to ALARM

## Services Used

* AWS EC2
* Amazon CloudWatch
* Amazon SNS
* Amazon Linux

## Architecture

EC2 Instance → CPU Utilization Metric → CloudWatch Alarm → SNS Topic → Email Notification

## Steps Performed

### 1. Opened CloudWatch

* Opened EC2 instance Monitoring tab
* Clicked View in CloudWatch
* Opened EC2 Per-Instance Metrics

### 2. Selected CPU Utilization Metric

* Selected CPUUtilization metric for EC2 instance
* Used Average statistic
* Used 5 minute period

### 3. Created CloudWatch Alarm

* Configured alarm when CPU Utilization is greater than 70%
* Used 2 out of 2 datapoints
* Created alarm named High-CPU-Usage-Alarm

### 4. Configured SNS Topic

* Created SNS topic named ec2-cpu-alert
* Added email subscription
* Confirmed subscription from email inbox

### 5. Triggered CPU Load

Used the following commands to increase CPU usage:

```bash
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
```

Stopped the processes using:

```bash
killall yes
```

### 6. Verified Alarm State Change

* Observed alarm state changing from OK to ALARM
* Received email notification from SNS
* Verified alarm returned to OK after CPU usage decreased

## Commands Used

```bash
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
top
killall yes
```

## Key Learnings

* Learned how CloudWatch monitoring works
* Learned how to create CPU alarms
* Learned how SNS email notifications work
* Learned how to generate CPU load manually
* Learned how to monitor EC2 performance
* Learned how to troubleshoot high CPU usage

## Challenges Faced

* SNS email subscription remained pending until email confirmation
* Alarm initially showed insufficient data
* CPU usage was low when only one process was running
* Solved issue by running multiple background CPU commands

## Project Output

The project successfully:

* Monitored CPU utilization
* Sent email alerts when CPU exceeded threshold
* Changed alarm state from OK to ALARM
* Returned alarm back to OK after CPU load stopped

