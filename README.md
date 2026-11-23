#!/bin/bash

echo "criando diretorios..."
mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec

echo "criando grupos..."
groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "criando usuarios..."
useradd -m carlos -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_ADM
useradd -m maria -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_ADM
useradd -m joao -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_ADM
useradd -m debora -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_VEN
useradd -m sebastiana -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_VEN
useradd -m roberto -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_VEN
useradd -m josefina -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_SEC
useradd -m amanda -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_SEC
useradd -m rogerio -s /bin/bash -p $(openssl passwd -6 201802) -G GRP_SEC

echo "criando permissoes..."
chmod 777 /publico
chmod 770 /adm
chmod 770 /ven
chmod 770 /sec

echo "criando donos..."
chown root:root /publico
chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec
