# crypt-utility-installer

Ansible install for cryptographic test VM software collection.

The playbook uses shell commands with apt-get and apt and is built for Ubuntu 22.

Example of running the Ansible play:
```
ansible-playbook -u root -i hosts.ini crypt-utility-installer.yml
```

Example of extracting all the shell commands and executing them instead of using Ansible:
```
grep shell crypt-utility-installer.yml | grep -v "name: shell" | cut -d ':' -f2- | bash - 
```

Example using for more specific installs:
```
cp crypt-utility-installer.yml pki.yml
vim pki.yml # cut out compilers and testers, customize with reduction
ansible-playbook -u root -i hosts.ini pki.yml
```


Installs:

<h2>cryptography stuff:</h2>
- gnupg2</br>
- age</br>
- openssl</br>
- cosign</br>
<h2>pki things:</h2>
- smallstep</br>
- hashicorp vault</br>
- certbot</br>
<h2>compilers</h2>
- go</br>
- cargo (rust)</br>
- g++ (c++)</br>
- gcc</br>
<h2>java stuff</h2>
- openjdk11</br>
- wycheproof</br>
- keycloak</br>
<h2>testing</h2>
- bazel</br>
- trivy</br>
- cargo clippy</br>
- sslscan</br>
- nmap</br>
- wasmtime (wasm runtime)</br>
<h2>build system</h2>
- syft (SBOM)</br>
- wasi (wasm)</br>
<h2>cloud client and testing things</h2>
- docker and docker-compose</br>
- kubectl</br>
- aws cli</br>
- gcp cli</br>
- azure cli</br>
