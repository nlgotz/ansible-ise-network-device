# Ansible ISE Network Devices

This project is a sample of how to add network devices with TACACS to Cisco ISE.

## How to run
1. Ensure that Cisco ISE has the API working [Good resource on how to enable ISE ERS API](https://community.cisco.com/t5/security-documents/ise-ers-api-examples/ta-p/3622623)
2. Make sure that you have a working username/password using something like curl or Postman
3. After cloning the repository, update the new-device-include.yml file with proper server credentials.
4. Run the playbook the following way:
   ```
   ansible-playbook -i localhost new-device.yml --extra-vars '{"devices": [{"profile_name": "Cisco", "ipaddress": "100.64.10.11", "name": "SWITCH01"}]}'
   ```


## Notes
- If there are multiple ISE servers, this will add it to the active server, no need to update the playbook if your active server changes
- This code is poorly commented and doesn't follow the way most Ansible modules should be written. My bad. If/when I get time, I'll update it.
