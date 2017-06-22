# Infraestrutura de TI do Câmpus São José

A CTIC atualmente administra em sua infra:

* 14 Servidores físicos
* 37 Switches gerenciáveis + alguns não ger.
* Firewall PFSense com redundância ativa de hardware 
* 25 APs Cisco
* 380 Computadores
* Central telefônica +/- 70 Ramais
* +30 Servidores Virtuais (Wiki, armazenamento, página web, Câmeras...)

Em 2016 começamos vários projetos para implementar técnicas de redundância nas várias camadas na nossa infraestrutora. Almejamos atingir um alto nível de maturidade, segurança e estabilidade da infra para dar suporte a outros projetos relacionados a mudança na forma como provemos e administramos os nossos serviços.

Foram constatados vários problemas como:

* Sem redundância de 
* * firewall (1 Cisco ASA)
* * servidor de arquivos
* * do core switch
* * dos virtualizadores
* Vários switches não gerenciáveis
* Sem documentação da infra
* Muito cabeamento  antigo (morto) nas calhas e racks
* Cobertura WIFI com problemas
* Sem gerenciamento remoto dos servidores
* Identificação do cabeamento estruturado desatualizada

### Infra anterior/atual(problemas): 

![Infra anterior](docs/infra_anterior_problemas.png)

### Infra atual/futuro(soluções): 

![Infra anterior](docs/infra_futura_redundancias.png)

### Segurança e estabilidade da nossa rede hoje:

![Rede anel](docs/redundancia_geografica_rede_interna.png)

Implementamos recentemente a redundância de Hardware ativa do nosso Firewall, um projeto que iniciou a um tempo quando constatamos que "o que aconteceria se nosso firewall Cisco ASA(desatualizado) queimasse?". Também, dentro do IFSC já estavam utilizando o PFSense como firewall e com excelentes resultados. Primeiramente substituimos para o PFSense e recentemente implementamos uma HA no nosso firewall. Ou seja, pode dar problema no nosso firewall master e o backup assume automaticamente. Utilizamos como [referência](https://doc.pfsense.org/index.php/High_Availability) a documentação oficial do PFSense.

### Vídeo da redundância funcionando:

[![Watch the video](https://img.youtube.com/vi/jkS7ZbTbtkA/0.jpg)](https://youtu.be/jkS7ZbTbtkA)

### Firewall PFsense  Master e Backup:
![PFsense HA](docs/pfsense_carp_master_backup.png)

### Hardwares diferentes onde rodam o PFSense:
![PFsense HA2](docs/pfsense_ha_hardware.png)
