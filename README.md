# Ansible-based Connectivity Validator
This repo contains the Ansible roles used to test the full mesh connectivity between your hosts.

## Purpose
This tool aims to help you with testing a full mesh connectivity between your nodes, both on IPv4 and IPv6. It was created as a helper tool for me to quickly test that network configurations created during development of network automation tools act preciesly as I expect: they either permit certain traffic flows or not; and I want to know that for sure.

## Compatibility
The tool was originally created and tested for Ubuntu Linux. Other distributions require further testing and, probably, playbooks' modification.

## How Does it Work?
The high-level workflow of the tool is the following:
1. It collects all the IPv4 and IPv6 addresses configred at Linux hosts in `ansible_facts`.
2. Once the data is collected, the joint list of all IPv4 and IPv6 addresses is build.
3. Then each host tries to reach all other IP addreses and document the result.
4. Finally, the joint report is produced

## Usage
In order to run the playbook, make sure you have Ansible Base 2.10+ version installed. The tool relies solely on `ansible.builtin` collection, so no extra collections are needed. To get a connectivity report:
1. Modify `hosts` file per your topology.
2. Run the playbook as `ansible-playbook validate_reachability.yaml`.
3. Wait...
4. Once the playbook is finished, check `output/report.txt` file.

## More details
This repository supports our blog [Karneliuk.com](https://karneliuk.com). Find the corresponding blogposts explaing these files.

## Want to be Automation Expert?
[Enroll to our Zero-To-Hero Network Automation Training](https://training.karneliuk.com/forms/). Study in online groups or in a self-paced mode.

## Need Help?
[Contact us](https://karneliuk.com/contact/) with your request and we will find the most suitable solution for you.

(c)2022, Karneliuk.com