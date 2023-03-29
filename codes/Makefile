all:
	sudo sysctl -w net.ipv4.ip_forward=1
	chmod +x mitm_attack 
	mkdir -p sslsplit_log
	sudo iptables -t nat -F
	sudo iptables -t nat -A PREROUTING -p tcp --dport 443 -j REDIRECT --to-ports 8443
	touch ~/.rnd
	openssl genrsa -out ca.key 4096
	openssl req -new -x509 -days 314 -key ca.key -out ca.crt -subj '/C=TW/O=NCTU/CN=jff'
clean:
	rm -rf sslsplit_log
	rm ca.key ca.crt
	rm mitm_attack

# pharm_attack dns_spoofing get_info