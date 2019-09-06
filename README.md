# Connection

É uma classe PHP para instanciar objetos PDO. Ela foi criada utilizando os padrões de projetos: Singleton e Factory

## Getting Started

O projeto tem como objetivo prover um meio inteligente e eficiente de instanciar objetos de conexão. A configuração deverá ser feita no arquivo configdb.ini. Connection é construida para não ser instanciada e portanto, quando tem seu método getInstance invocado, em si mesma deverá carregar o arquivo configdb.ini e ler as configurações para instanciar o objeto PDO corretamente.

### Prerequisites

Você precisa ter instalado PHP e MySQL Server. Se estiver utilizando Linux, muitas vezes o LAMP lhe apresentará todo ambiente perfeito. No Windows, muitos costumam utilizar o XAMP.
Não faz parte desde documento, apresentar as etapas de instalação de cada elemento do ambiente.

### Installing

Após baixar o código, se estiver compactado, extrai-os e coloque-os em um diertório que possa ser lido por um servidor web ou em um diretório de sua preferencia para rodar com o servidor web embutido no php.
 
Além disso, você precisa configurar as definições do seu servidor no arquivo configdb.ini:

```ini
; Arquivo de configuração de conexão com o banco de dados
; Driver de conexão
sgdb      = mysql
; Dados para conexão
banco     = crudsimples
servidor = localhost
porta     = 3306
; Credenciais de usuário
usuario  = root
senha    = P@ssw0rd
```

O que você definir em seu ambiente, deverá refletir aí.


Após isso, você deve estar certo de que o script esteja em um diretório que possa ser lido pelo servidor web local ou, que tenha permissões suficiente de acesso ao diretório para utilizar o servidor embutido do php. 
Em geral para se utilizar o servidor embutido, utiliza-se o seguinte comando no diretório do projeto:

```
php -S localhost:8080

```

Após inicia o servidor embutido, será possível invocar o programa no browser através de um endereço URL como:

```
http://localhost:8080

```

### Usage

Primeiramente você precisa importar a classe. Feito isso, invoque o método getInstance() passando como argumento o caminho do arquivo configdb.ini.
Se as configurações estiverem corretas, uma instancia de objeto pdo deverá ser devolvida.

```php

include './Connection.php';

$con = connection::getInstance('./configdb.ini');

echo (is_a($con, PDO))?'Instanciado com êxito' :'Não deu certo!';

```

## Authors

* **Alexandre Bezerra Barbosa**
