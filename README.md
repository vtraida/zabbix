# zabbix
based on centos 7
run - "ansible-playbook -i hosts zabbix_install_file.yml -l zabbix-test-vm02"
where zabbix-test-vm02 - is your destination server, change ip in hosts file

role - resolve_hotfix_SE_issue
include compiled modules for SE Linux
