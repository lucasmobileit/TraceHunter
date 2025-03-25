# TraceHunter - Forensic Collector
Descrição
O TraceHunter é um script em Bash projetado para coletar informações forenses de um sistema Linux. Ele reúne dados relevantes sobre discos, conexões de rede, processos em execução, logs do sistema e arquivos de configuração, organizando tudo em um diretório específico para facilitar a análise posterior.

## Pré-requisitos
O script deve ser executado em um sistema Linux.
É necessário ter permissões de superusuário (root) para executar o script corretamente.

## Instalação
Clone o repositório ou baixe o script para o seu sistema.
Dê permissão de execução ao script:
chmod +x TraceHunter.sh

## Uso
Para executar o script, utilize o seguinte comando:
sudo ./TraceHunter.sh

### Observações
O script verifica se está sendo executado como root. Se não estiver, ele exibirá uma mensagem de erro e encerrará a execução.
Todos os arquivos coletados serão armazenados em um diretório chamado collected_files, que será criado automaticamente.

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
