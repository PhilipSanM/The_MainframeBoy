## MLZ1:

---

1.- Get the VM.
	*GitHub repo -> https://github.com/linuxone-community-cloud/technical-resources/blob/master/faststart/deploy-virtual-server.md
	*Link -> https://linuxone.cloud.marist.edu/#/login
	*Putty -> https://github.com/linuxone-community-cloud/technical-resources/blob/master/faststart/PUTTY_Set_up.pdf

---

2.- Open a secure shell connection and install docker runtime


curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh
sudo usermod -aG docker $USER; newgrp docker
sudo systemctl start docker
exec bash


sudo iptables -I INPUT -p tcp --dport 38888 -j ACCEPT
sudo bash -c "iptables-save > /etc/iptables/rules.v4"

---

3.- Start Jupyter Lab container on the port 38888

docker login -u l1cc registry.linuxone.cloud.marist.edu     

			 -Psswrd : Linux0NE

docker run -p 38888:8888 --name notebook --rm \
-v /home/linux1/jupyter:/home/jovyan/shared \
-d registry.linuxone.cloud.marist.edu/jupyterlab-image-s390x:latest \
jupyter lab --ServerApp.token='L1Hackathon'

---

4.- Connect to JupyetLab
 ip address | grep "global enc1000"

http://148.100.79.8:38888/


Auth    psswdr-> L1Hackathon

----

5.- GG
docker stop notebook

----

6.- 
	Download the model

	ssh z19140@204.90.115.200

	scp Downloads\customer_churn.onnx z19141@204.90.115.200:/z/z19141


	ZXP.PUBLIC.JCL(CHKMLZ1) 
