# ansible-security-settings
Ansible Role for enforcing security settings related to enterprise compliance on enterprise grade OS

## Description

This role configures several security settings across login, password management, ssh, pam, selinux configuration and other. It is designed for enterprise compliance definitions.

Configures:

* pam tally and faillock modules for automated account lockout on failures
* password history for no reuse
* password complexity
* restrict root logins to system console

Variables:

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `os_auth_pw_max_age` | 60 | Max days a password is valid before requiring a change |
| `os_auth_pw_min_age` | 10 | Min days of age a password must have before it can be changed |
| `fail_deny` | 5 | Amount of times failed password can be tried before locking the account |
| `fail_unlock` | 300 | Seconds that must pass before account is unlocked after failed logins |
| `pwquality_minlen` | 8 | Minimum password length in characters |
| `pwquality_maxrepeat` | 3 | Maximum amount of same characters repeated in password |
| `pwquality_lcredit` | -1 | lowercase amount of chars that must be present in password |
| `pwquality_ucredit` | -1 | uppercase amount of chars that must be present in password |
| `pwquality_dcredit` | -1 | digits that must be present in password | 
| `pwquality_ocredit` | -1 | special chars that must be present in a password |
| `passhistory` | 6 | number of password to remember to avoid reusage |
| `sshrootlogin` | 'no' | allow ssh root login, keep single quotes to avoid boolean evaluation |
| `sshmainport` | 22 | main ssh port |
| `sshextraport` | 32 | secondary ssh port |
| `setloginbanner` | 'yes' | use a login banner in ssh, keep single quotes to avoid boolean evaluation |
