#### Step1: download prometheus to loacl machine
```
wget https://github.com/prometheus/prometheus/releases/download/v2.30.0-rc.0/prometheus-2.30.0-rc.0.linux-amd64.tar.gz
```
#### Step2: Unzip downlaoded file 
```
tar -xvf prometheus-2.30.0-rc.0.linux-amd64.tar.gz
```
#### step3: goto promotheus folder
```
cd prometheus
```
#### Step4: Start prometheus

```
./prometheus
```

### To start prometheus as service please follow below steps 

#### Step:5 copy prometheus into /usr/loacl/bin/prometheus
```
cp -r . /usr/local/bin/prometheus
```

#### Step6: edit prometheus.service file and copy below content 

```
vi /etc/systemd/system/prometheus.service
```

### copy below to prometheus.service

```
[Unit]
Description=Prometheus Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/prometheus/prometheus --config.file=/usr/local/bin/prometheus/prometheus.yml

[Install]
WantedBy=multi-user.target
```
#### Step7:  To Start prometheus as service 
```
sudo service prometheus start
```
