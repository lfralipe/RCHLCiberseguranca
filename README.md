# Desafio DIO de Segurança

##  **Riachuelo - Cibersegurança** da DIO. 
Este projeto tem com objetivo demonstrar, em ambiente controlado, a execução de ataques de **BRUTEFORCE** utilizando a ferramenta Medusa no KALI Linux.

**Obs.** Este é um projeto meramente educativo. Todos os testes foram realizados em laboratório isolado para fins educacionais.



### Ambiente e Ferramentas
- VirtualBox - Ferramenta de virtualização da Oracle
- Kali Linux - SO baseado em Linux que possui diversas ferramentas para testes de invasão
- Metasploitable 2 - SO baseado em Linux intencionalmente vulnerável que irá ajudar na nossa tarefa.
- DVWA - É uma aplicação web vulnerável que forneceram um formulário que iremos explorar.


### Rede
- Maquinas virtuais configurada como Host-Only
- IP Kali: 192.168.1.2
- IP Metasploitable: 192.168.1.3
**Obs.** Os IPs foram configurados manualmente.

* [Configuração REDE KALI](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/kali_rede001.png)
* [Configuração REDE Metasploitable](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/metasploitable_rede001.png)


### Primeira fase do ataque - Descoberta dos serviços
- Comando -> nmap -p 21 -sV 192.168.1.3
* [NMAP](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_nmap001.png)

### Segunda fase do ataque - Medusa - ataque de força bruta.
**Obs** Como é apenas um simples teste, para executar está tarefa criei um dicionário com apenas uma senha "msfadmin".
- Comando -> medusa -h 192.168.1.3 -u msfadmin -P lista_senhas.txt -M ftp
    - O comando acima funciona como: medusa é o app, o -h informa o alvo, -u msfadmin informa que irá atrás do usuário msfadmin, caso eu tivesse uma lista passaria o -U lista_usuarios.txt
      -P lista_senha.txt é a lista de password e o -M ftp informa o serviço que será o alvo.
* [MEDUSA](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_medusa001.png)


### Ataque de Força Bruta em Formulários de Login Web

   * Primeira fazer verificar qual as requisições que o site faz. [Requisição](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_formulario001.png)
   * Segundo utilização ou criação de wordlist com nome de usuários e senhas
   * Terceiro fazer ataque com medusa [Ataque](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_formulario002.png)
   * Quarto obter o resultado [Resultado](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_formulario003.png)


### Ataque enumeração SMB
   * Primeiro rodar -> enum4linux 192.168.1.3
   * Usar o medusa para conseguir a senha [medusa](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_smb001.png)
   * Testando a senha [Senha](https://github.com/lfralipe/RCHLCiberseguranca/blob/main/ataque_smb002.png)

**Este foi o nosso desafio.**
