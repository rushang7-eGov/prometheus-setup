# prometheus-setup
 
## Install InfluxDB

Values to configure:

.Values.persistence.size

`helm install charts/stable/influxdb --name influxdb --namespace monitoring`

Create a database in InfluxDB. 

For example, 

`CREATE DATABASE "<db-name>"`

Save InfluxDB Credentials : \<influxdb-user\> and \<influxdb-password\>

Default user : admin

Default password can be set by the value : .Values.setDefaultUser.user.password

## Install Prometheus


