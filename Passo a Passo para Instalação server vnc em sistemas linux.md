# Passo a Passo para Instalação server vnc em sistemas linux.

### Para iniciarmos a instalação, primeiro é necessário atualizar seu repositório, com o seguinte comando:

#####                              

#####     sudo apt update

=====================================================================

### Em seguida instale a seguinte aplicação:



#####         sudo apt install lightdm

======================================================================

###  Restart a Maquina com o Seguinte comando:



##### sudo reboot

======================================================================

### Aqui começaremos o processo de Intalação de nosso Servidor VNC.

#### >>>É importante que os passos a seguir sejam feitos de acordo com as instruções:<<<



### Instalar servidor vnc



##### sudo apt install x11vnc

=====================================================================

### Após a instalação execute o seguinte comando em seu terminal:



##### sudo nano /lib/systemd/system/x11vnc.service

======================================================================

### Copie os seguintes comandos e configure o seu password no campo 'SUA SENHA'

[Unit]
Description=x11vnc service
After=display-manager.service network.target syslog.target

[Service]
Type=simple
ExecStart=/usr/bin/x11vnc -forever -display :0 -auth guess -passwd **SUA SENHA**
ExecStop=/usr/bin/killall x11vnc
Restart=on-failure

[Install]
WantedBy=multi-user.target

======================================================================



### Pronto, agora salve os arquivos e executes os seguintes comandos:



systemctl daemon-reload
systemctl enable x11vnc.service
systemctl start x11vnc.service
systemctl status x11vnc.service

=======================================================================

# Seu servidor vnc está configurado e pronto para uso. Bons Estudos!



