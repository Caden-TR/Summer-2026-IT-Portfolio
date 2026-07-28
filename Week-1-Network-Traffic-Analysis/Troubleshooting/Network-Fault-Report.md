# Network Fault Troubleshooting Report

## Overview

This exercise involved intentionally creating a network fault within a simple LAN in Cisco Packet Tracer. The aim was to investigate the issue, identify the cause, implement a solution, and verify that normal network communication had been restored.

## Problem

A connectivity issue was introduced by changing the IP address of PC1 from **192.168.1.11** to **192.168.1.50**. As a result, PC0 was no longer able to communicate with PC1 using the original IP address.

## Investigation

To confirm the fault, a ping test was performed from PC0 to **192.168.1.11**. The test failed, indicating that the destination device could not be reached.

The IP configuration of both devices was then checked. PC0 was correctly configured, while PC1 had been assigned an incorrect IP address, explaining why the ping request failed.

## Cause

The issue was caused by an incorrect IP address being configured on PC1. Since PC0 was attempting to communicate with **192.168.1.11**, but PC1 was configured as **192.168.1.50**, there was no device using the expected address.

## Resolution

The IP address of PC1 was changed back to **192.168.1.11**, restoring the original network configuration.

## Verification

A second ping test was performed from PC0 to **192.168.1.11** after correcting the configuration.

The test completed successfully with:

* 4 packets sent
* 4 packets received
* 0% packet loss

This confirmed that communication between both devices had been restored.

## Reflection

This exercise demonstrated the importance of correct IP addressing in a local area network. Even a simple configuration error can prevent devices from communicating successfully. By following a structured troubleshooting process—identifying the problem, investigating the configuration, correcting the fault, and verifying the solution—I was able to restore network connectivity efficiently. This practical exercise also reinforced the value of systematic troubleshooting, an essential skill for networking and cyber security professionals.
