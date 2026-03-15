# nota-samba
Notas importante

<h1>Intalando o Samba </h1>

  	sudo apt install samba
<br/>
<p>Backup do arquivo padão</p>

	sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.bkp
<br/>
<p>Restartar o samba</p>

	sudo systemctl restart smbd
<br/>
<p>modelo de arquivo SMB</p>

 	[global]
	server string = %h server (Samba, Arch)
	map to guest = Bad User
	null passwords = Yes
	guest account = willian
	time server = Yes
	socket options = SO_SNDBUF=2048 IPTOS_THROUGHPUT=1

	[Documentos]
	comment = Notebook Willian
	path = /home/willian/Documentos/vmware/
	guest only = Yes
	guest ok = Yes

	[nome_do_compartilhamento]
    comment = Descrição do compartilhamento
    path = /caminho/para/o/diretorio
    browseable = yes
    read only = no
    writeable = yes
    valid users = <nome_do_usuario>
<br/>
<p>Adicionando usuario ao samba</p>

 	smbpasswd -a nome_usuario
</br>

<p>Dono da pasta</p>

 	sudo chown administrador:administrador /var/www/html
</br>
