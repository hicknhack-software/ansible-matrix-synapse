This code will install matrix-synapse on your server & get an certificates from `letsencrypt.org` for your domain, and set a cron job to renew the certificates.

**Tested:**  
 - Ubuntu Xenial (16.04)

**Minimum Requirements:**
 - Ubuntu >= 16.04
 - Vagrant >= 1.7.0 (If your staging server is vagrant, if not, this is not applicable)
 - ansible >=2.0

**Be mindful you need to set the variables before running the script; the variables are to be set in the defaults/main.yml file**
 - Send anonymus stats report to help improve matrix code, VISIT: matrix.org
     - matrix_synapse_report_stats: true/false
 - The domain of server where you plan to set homeserver. (Eg: www.MY_AWESOME_WEBSITE.com)
     - matrix_synapse_hostname: vagrant.box
 - Amount of RAM matrix-synapse is allowed to use, Read more at https://github.com/matrix-org/synapse#help-synapse-eats-all-my-ram
     - matrix_synapse_cache_factor: INTEGER
 - Set to `true` if you plan to allow users to register themselves using riot.im like clients, Set `false` otherwise.
     - matrix_synapse_enable_registration: true/false

**How to run:**
  1. Install Ansible
  2. Add your server group in the inventory.
  3. Change the `hosts` from `all` to the server group in which you want to install matrix-synapse. (In file ansible-matrix-synapse/main.yaml) [optional; as per your Requirements]
  4. Change the `remote_user` from `root` to a user which is a sudoer. (In file ansible-matrix-synapse/main.yaml) [optional; as per your Requirements]
  5. Make sure you have set the variables you desire for installation. (In file ansible-matrix-synapse/defaults/main.yaml)
  6. Run the following command (from inside the ansible-matrix-synapse folder): `ansible-playbook main.yaml --ask-become`

- Ansible: https://www.ansible.com
- Matrix: https://matrix.org/
- letsencrypt: https://letsencrypt.org/

**Feel free to contribute in this Repository or open an issue.**
