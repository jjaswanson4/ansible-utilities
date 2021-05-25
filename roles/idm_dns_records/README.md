# idm_dns_records

Ansible role to manage DNS records in an IDM/IPA environment.

# Inputs

The role expects a dictionary containing information about the idm/ipa environment with a nested list of records to manage:
```yaml
dns:
  server: example01.company.com
  password: changeme
  records:
    - name: server01
      zone: company.com
      type: A
      value: 10.0.0.5
    - name: 5
      zone: 0.0.10.in-addr.arpa.
      type: PTR
      value: server01.company.com.
```
# Outputs
The above example would create the following two records:
- `example01.company.com A 10.0.0.5`
- `10.0.0.5 PTR server01.company.com.`