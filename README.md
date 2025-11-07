# LABORATORIOS-MODULO-VI-SOIII-
#!/bin/bash
# Instalar gpg2
sudo apt update && sudo apt install gnupg2  # Debian/Ubuntu
# o
sudo yum install gnupg2  # Red Hat/CentOS

# Crear directorio y archivo
mkdir mi_directorio_cifrado
cd mi_directorio_cifrado
echo "Este es un archivo secreto de prueba" > archivo_secreto.txt

# Generar par de claves (si no tienes)
gpg2 --gen-key
# Seguir los pasos para generar la clave

# Cifrar el archivo
gpg2 -c archivo_secreto.txt
# Te pedirá una passphrase para cifrar

# Ver archivos (verás el cifrado)
ls -la
# archivo_secreto.txt.gpg

# Intentar acceder al archivo cifrado
cat archivo_secreto.txt.gpg
# Verás contenido binario/ilegible

# Descifrar el archivo
gpg2 -d archivo_secreto.txt.gpg > archivo_descifrado.txt
# Te pedirá la passphrase

# Ver contenido descifrado
cat archivo_descifrado.txt
sudo iptables -A INPUT -p tcp --dport 80 -j DROP
sudo iptables -A INPUT -p tcp --dport 21 -j DROP
sudo iptables -A INPUT -p tcp --dport 22 -j DROP

# Ver reglas
sudo iptables -L

# Habilitar nuevamente con IP tables
sudo iptables -D INPUT -p tcp --dport 80 -j DROP
sudo iptables -D INPUT -p tcp --dport 21 -j DROP
sudo iptables -D INPUT -p tcp --dport 22 -j DROP
sudo firewall-cmd --permanent --remove-service=http
sudo firewall-cmd --permanent --remove-service=ftp
sudo firewall-cmd --permanent --remove-service=ssh
sudo firewall-cmd --reload

# Ver estado
sudo firewall-cmd --list-all

# Habilitar nuevamente con firewall-cmd
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=ftp
sudo firewall-cmd --permanent --add-service=ssh
sudo firewall-cmd --reload
