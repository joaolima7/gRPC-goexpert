# Configuração do gRPC com Go
Para utilizar o gRPC com Go, é necessário seguir alguns passos de instalação e configuração.
## Passo 1: Instalar o Protobuf
Primeiramente, você precisa instalar o Protobuf. Se estiver utilizando um sistema baseado em macOS, pode fazer isso com o Homebrew:

```bash
brew install protobuf
```
Após a instalação, verifique se o Protobuf foi instalado corretamente executando o seguinte comando:

```bash
protobuf --version
```
## Passo 2: Instalar os Plugins do Protobuf para Go
Em seguida, você precisa instalar os plugins do Protobuf para Go. Execute os seguintes comandos:

```bash
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```
Esses comandos instalarão os plugins necessários para gerar código Go a partir dos arquivos `.proto`.
