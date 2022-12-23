# Aviso aos desavisados
- Caso esteja rodando no WSL não esqueça de executar o comando "sysctl -w vm.max_map_count=262144" antes de dar o docker-compose up.
- Na versão 8 do kibana os "Index patterns" foram renomeados para "data views"
- Esses composes sobem o Elastic Search com a segurança desabilitada, NÃO use em produção.
- Se quiser algo para produção leia a documentação no site da elastic https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html 
