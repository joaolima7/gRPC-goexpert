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


## Passo 3: Gerar Código Go a partir dos Arquivos `.proto`
Para gerar o código Go a partir dos arquivos `.proto`, você deve usar o comando `protoc` com os plugins instalados. Por exemplo, se você tiver um arquivo chamado `course_category.proto`, execute o seguinte comando:

```bash
protoc --go_out=. --go-grpc_out=. proto/course_category.proto
```
Esse comando irá gerar os arquivos Go necessários para o serviço gRPC definido no arquivo `.proto`. O parâmetro `--go_out=.` especifica o diretório de saída para os arquivos gerados, enquanto `--go-grpc_out=.` indica que você também deseja gerar o código específico do gRPC.

## Passo 4: Instalar o Evans (opcional)
Para facilitar a interação com o gRPC, você pode instalar o Evans, que é uma ferramenta de linha de comando para interagir com serviços gRPC. Para instalá-lo, execute o seguinte comando:

```bash
go install github.com/ktr0731/evans@latest
```
Após a instalação, você pode acessar o Evans com o comando:

```bash
evans -r repl
```
Dentro do Evans, você pode visualizar os pacotes disponíveis com o comando:

```bash
show package
```
E para usar um pacote específico, você pode executar:

```bash
package pb
```
Para chamar um método gRPC, como `CreateCategory`, você pode usar o comando:

```bash
call CreateCategory
```
E então inserir os valores necessários para a chamada.