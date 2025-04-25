# TraceHunter - Forensic Collector
Descrição
O TraceHunter é um script em Bash projetado para coletar informações forenses de um sistema Linux. Ele reúne dados relevantes sobre discos, conexões de rede, processos em execução, logs do sistema e arquivos de configuração, organizando tudo em um diretório específico para facilitar a análise posterior.

## Pré-requisitos
O script deve ser executado em um sistema Linux.
É necessário ter permissões de superusuário (root) para executar o script corretamente.

## Uso
Para executar o script, utilize o seguinte comando:
sudo ./TraceHunter.sh -> Certifique de ter dado permissão de execução para o script (chmod +x)

## O script coleta as seguintes informações

### Informações sobre discos e partições:
Saída do comando lsblk armazenada em collected_files/disk_info.txt.

### Informações de rede:
Conexões ativas com ss em collected_files/active_connections.txt.
Portas abertas com netstat em collected_files/open_ports.txt.

### Lista de processos:
Saída do comando ps aux em collected_files/process_list.txt.

### Logs do sistema:
Cópias dos logs do sistema localizados em /var/log/:
syslog em collected_files/syslog.log
auth.log em collected_files/auth.log
dmesg em collected_files/dmesg.log

### Arquivos de configuração:
Cópia do diretório /etc em collected_files/backup.

### Diretório raiz:
Listagem do diretório raiz em collected_files/root_dir_list.txt.

### Arquivo compactado:
O conteúdo do diretório collected_files será compactado em um arquivo .tar.gz nomeado como TraceHunter_<hostname>_<data_hora>.tar.gz.
