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

Values to configure:

.Values.serverFiles.prometheus.yml.remote_write.url
.Values.serverFiles.prometheus.yml.remote_read.url

remote_write.url : "http://influxdb.monitoring:8086/api/v1/prom/write?db=\<db-name\>&u=\<influxdb-user\>&p=\<influxdb-password\>"

remote_read.url : "http://influxdb.monitoring:8086/api/v1/prom/read?db=\<db-name\>&u=\<influxdb-user\>&p=\<influxdb-password\>"

`helm install charts/stable/prometheus/ --name prometheus --namespace monitoring`


