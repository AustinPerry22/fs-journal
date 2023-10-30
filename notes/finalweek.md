aws and azure are the most popular web solutions
easy for 300$ mistakes

local routers assign local ip address
you can subnet ip addresses so more than 255 people can connect

local networks talk to a single Ip address given by the router

ec2 - make a new vm take a tiny piece of the data server
when you pick a region make sure its only the oregon one or else it will charge you money

when you launch an instance be careful
make sure the server says free tier eligable
Don't use windows use ubuntu
use x86
make sure the instance type is free tier eligable

create a new key pair

configure the firewall section

- allow ssh traffic from anywhere
- allow http/https traffic from internet
- DO NOT store sensitive information

make sure to give a security group name -defualt open everything demos only
add a MYSQL/Aurora anywhere

make sure you have your keypair
to connect to your newly created server

ssh -i "~/source/aws/yourkey.pem" unbunto@ipaddressofserver
yes

now your in the server command line
sudo apt update
sudo apt upgrade
y
sudo apt install mysql-server -y
sudo systemctl enable mysql
sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'my password';
to reaccess your mysql use
sudo mysql -p
exit
sudo mysql_secure_instillation
y

\*a mysql server can have as many databases as you want
