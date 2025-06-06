# 2025_-
사물인터넷 1학기 코딩 보관

# InfluxDB 설치
- InfluxDB download key using wget

```bash
wget -q https://repos.influxdata.com/influxdata-archive_compat.key
echo '393e8779c89ac8d958f81f942f9ad7fb82a25e133faddaf92e15b16e6ac9ce4c influxdata-archive_compat.key' | sha256sum -c && cat influxdata-archive_compat.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg > /dev/null
echo 'deb [signed-by=/etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg] https://repos.influxdata.com/debian stable main' | sudo tee /etc/apt/sources.list.d/influxdata.list
```

- Packages are up to date && install Influxdb

```bash
sudo apt-get update && sudo apt-get install influxdb -y
```

- InfluxDB as a background service on startup

```bash
sudo service influxdb start
```


- InfluxDB is status (service)
```bash 
sudo service influxdb status
```

# InfluxDB 데이터베이스 만들기
```bash
$ influx

>create database <데이터베이스이름>
확인 : show databases
```

# influxdb import with python
```bash
pip install influxdb
```
# Grafana Installation

# 1. Install the prerequisite packages

```bash
sudo apt-get install -y apt-transport-https software-properties-common wget
```

# 2. Import the GPG key:

```bash
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

# 3. To add a repository for stable releases, run the following command:

```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

# 4. Run the following command to update the list of available packages:

```bash
sudo apt-get update && sudo apt-get install grafana -y
```

# 5. Run the following command to server start

```bash
sudo systemctl start grafana-server
```
