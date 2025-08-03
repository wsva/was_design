was - wsva automation system

# 1 components

## 1.1 auth, assets etc.
| name                                                       | function                                       | language |
|------------------------------------------------------------|------------------------------------------------|----------|
| [auth_service](https://github.com/wsva/auth_service)       | verify login, token                            | Go       |
| [asset_service](https://github.com/wsva/asset_service)     | machines, passwords and deployments management | Go       |
| [config_service](https://github.com/wsva/config_service)   | provide config to every machine                | Go       |
| [generate_pki](https://github.com/wsva/generate_pki)       | generate ca and server certificates            | Go       |
| [database_design](https://github.com/wsva/database_design) | tables, views and scripts                      | SQL      |

## 1.2 monitor
a monitoring system based on zabbix

| name                                                              | function                        | language      |
|-------------------------------------------------------------------|---------------------------------|---------------|
| [monitor -> zabbix](https://github.com/wsva/monitor_zabbix)       | zabbix agent management         | Python, Shell |
| [monitor -> collector](https://github.com/wsva/monitor_collector) | collect metrics form agent      | Go            |
| [monitor -> viewer](https://github.com/wsva/monitor_viewer)       | view monitor results in browser | Go            |

### 1.2.1 gather metrics (gm)
gather monitor metrics, called by zabbix agent

| name                                                                   | function                                  | language |
|------------------------------------------------------------------------|-------------------------------------------|----------|
| [gm_host](https://github.com/wsva/gm_host)                             | check cpu, memory, disk usage             | Python   |
| [gm_oracle](https://github.com/wsva/gm_oracle)                         | check ASM, tablespace, locks in oracle db | Go       |
| [gm_oracle_ogg](https://github.com/wsva/gm_oracle_ogg)                 | check Oracle GoldenGate status            | Python   |
| [gm_oracle_rman](https://github.com/wsva/gm_oracle_rman)               | check Oracle RMAN errors (locally)        | Python   |
| [gm_oracle_rman_remote](https://github.com/wsva/gm_oracle_rman_remote) | check Oracle RMAN errors (remotely)       | Go       |
| [gm_linux_service](https://github.com/wsva/gm_linux_service)           | check if linux service is running         | Go       |
| [gm_port](https://github.com/wsva/gm_port)                             | check if the port is open (tcping)        | Go       |
| [gm_web_service_soap](https://github.com/wsva/gm_web_service_soap)     | check if web service available (SOAP)     | Go       |

# 2 service ports
| service        | http port | https port |
|----------------|-----------|------------|
| auth_service   | 22001     | 33001      |
| asset_service  | 22002     | 33002      |
| config_service | 22003     | 33003      |