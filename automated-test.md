# Automated Security Testing
## Nikto
	nikto -h http://10.0.2.4

## SQLmap

* sqlmap -u http://192.168.43.201/example.php?name=root -b
* sqlmap -u http://192.168.43.201/example.php?name=root --dbs
  - dbs => list all databases
  -	-D exercises --tables => list all tables
  - -D excercises -T users --columns => list all columns
  - --dump-all
  - -D exercises -T users --dump
  - -D exercises --dump

## arachni
### Installation
1. wget <https://github.com/Arachni/arachni/releases/download/v1.5.1/arachni-1.5.1-0.5.12-linux-x86_64.tar.gz>
2. tar -xvzf arachni….
3. cd arachni….
4. ./arachni_web

### Quick start
#### Graphic User Interface(GUI)
* arachni_web => <http://localhost:9292>

#### Command Line(CLI)
* arachni --checks=xss* --report-save-path report http://10.0.2.4
* arachni_reporter report/web4pentester.afr 
				  --reporter=html:outfile=web4pentester.html.zip

## Gauntlt 
###Installation Guide
* cd /home
* git clone https://github.com/gauntlt/gauntlt
* cd gauntlt
* source ./install_gauntlt_deps.sh
* bash ./ready_to_rumble.sh
* gauntlt

### Examples
* Gauntlt main repo: <https://github.com/gauntlt/gauntlt/tree/master/examples>
* Gauntlt-demo repo: <https://github.com/gauntlt/gauntlt-demo/tree/master/examples>

## w3af
### Installation Guide
1. git clone
2. apt-get install -y libssl-dev libffi-dev
3. apt-get install -y libxml2-dev libxslt1-dev
4. Install npm
5. sh /tmp/w3af_dependency_install.sh

### Quick start
1. Cd /opt/w3af
2. ./w3af_console



