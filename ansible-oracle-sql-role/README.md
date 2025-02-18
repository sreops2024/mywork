# Ansible Oracle SQL Role

This Ansible role is designed to execute Oracle SQL scripts in a database environment. It provides a structured way to run SQL files, check for errors, and log the output for review.

## Role Variables

The following variables can be defined in `vars/main.yml` or overridden in your playbook:

- `oracle_db_user`: The username for the Oracle database.
- `oracle_db_password`: The password for the Oracle database user.
- `oracle_db_host`: The hostname or IP address of the Oracle database.
- `oracle_db_port`: The port number for the Oracle database (default is 1521).
- `sql_file_path`: The path to the SQL file that needs to be executed.
- `log_file_path`: The path where the log file will be created.

## Prerequisites

- Ansible installed on your control machine.
- Oracle client installed on the target machine where the SQL scripts will be executed.
- Proper network access to the Oracle database.

## Usage

To use this role, include it in your playbook as follows:

```yaml
- hosts: your_target_hosts
  roles:
    - ansible-oracle-sql-role
```

Make sure to define the necessary variables in your playbook or inventory file.

## Example

Here is an example of how to define the variables in your playbook:

```yaml
- hosts: your_target_hosts
  vars:
    oracle_db_user: "your_username"
    oracle_db_password: "your_password"
    oracle_db_host: "your_db_host"
    oracle_db_port: 1521
    sql_file_path: "/path/to/your/script.sql"
    log_file_path: "/path/to/your/logfile.log"
  roles:
    - ansible-oracle-sql-role
```

## Logging and Error Handling

The role will create a log file at the specified `log_file_path`. After executing the SQL script, it will check the log file for any Oracle errors and display the content of the log file for review.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.