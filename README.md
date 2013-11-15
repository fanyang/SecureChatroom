Safe Chat Room
===============
A safe Client-Server GUI chat room. Communication protocol is encapsulated in XML and encrypted
by SSL socket.

		Generate server keystore:
		keytool -genkey -v -alias ssl-chatroom-server -keyalg RSA -keystore ./server_ks -dname "CN=localhost,OU=cn,O=cn,L=cn,ST=cn,C=cn" -storepass server456 -keypass def456
		
		Generate client keystore:
		keytool -genkey -v -alias ssl-chatroom-client -keyalg RSA -keystore ./client_ks -dname "CN=localhost,OU=cn,O=cn,L=cn,ST=cn,C=cn" -storepass client789 -keypass abc789
		
		Export server certificate:
		keytool -export -alias ssl-chatroom-server -storepass server456 -keystore ./server_ks -file server_key.cer
		
		Import server certificate into client keystore:
		keytool -import -trustcacerts -alias ssl-chatroom-server -storepass client789 -file ./server_key.cer -keystore ./client_ks
