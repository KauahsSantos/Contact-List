# 📱 Contact List

Um projeto simples de **lista de contatos desenvolvido em Dart**, executado diretamente pelo terminal. O projeto foi desenvolvido com o objetivo de praticar conceitos fundamentais da linguagem Dart, como `Map`, funções, estruturas condicionais, loops, entrada de dados pelo terminal e manipulação de coleções.

---

## 📌 Sobre o projeto

O **Contact List** é uma aplicação de linha de comando que permite ao usuário gerenciar uma lista de contatos.

A aplicação utiliza um `Map<String, String>` para armazenar os contatos, onde:

* A **chave (`String`)** representa o nome do contato.
* O **valor (`String`)** representa o número de telefone.

Os dados ficam armazenados apenas em memória enquanto o programa está em execução. Ao fechar o programa, os contatos são perdidos.

---

## 🚀 Funcionalidades

A aplicação possui um menu interativo com as seguintes opções:

```text
1 - Adicionar contato
2 - Listar contato
3 - Atualizar contato
4 - Remover contato
5 - Buscar contato
6 - Sair contato
```

### ➕ Adicionar contato

Permite cadastrar um novo contato informando:

* Nome
* Número de telefone

O contato é armazenado dentro do `Map`.

```dart
listaContato[nome] = number;
```

---

### 📋 Listar contatos

Exibe todos os contatos cadastrados utilizando o método `forEach()`.

```dart
listaContato.forEach(
  (key, value) => print("$key - $value"),
);
```

Caso a lista esteja vazia, o programa informa que não existem contatos cadastrados.

---

### ✏️ Atualizar contato

Permite alterar o número de telefone de um contato existente.

O método `update()` do `Map` é utilizado para substituir o valor associado ao nome.

```dart
listaContato.update(nome, (number) => newNumber);
```

---

### 🗑️ Remover contato

Permite remover um contato utilizando seu nome.

Para isso, é utilizado o método `remove()`:

```dart
listaContato.remove(rm);
```

---

### 🔎 Buscar contato

Permite verificar se determinado contato existe na lista.

O método `containsKey()` é utilizado para verificar a existência do nome dentro do `Map`.

```dart
listaContato.containsKey(n2);
```

---

### 🚪 Sair

A opção `6` encerra o loop principal da aplicação.

```dart
while (input1 != 6) {
  // ...
}
```

---

# 🛠️ Tecnologias utilizadas

O projeto foi desenvolvido utilizando:

* **Dart**
* **Dart SDK**
* **Dart `dart:io`**
* Terminal / linha de comando
* Git
* GitHub

O projeto **não utiliza frameworks ou pacotes externos**.

---

# 📦 Biblioteca utilizada

## `dart:io`

A biblioteca nativa `dart:io` é utilizada para permitir a interação com o terminal.

```dart
import 'dart:io';
```

Ela é utilizada principalmente para:

### Entrada de dados

```dart
stdin.readLineSync();
```

Permite receber informações digitadas pelo usuário.

### Saída no terminal

```dart
stdout.write();
```

Utilizada para escrever diretamente no terminal.

### Limpeza do terminal

```dart
stdout.write('\x1B[2J\x1B[0;0H');
```

Utilizada para limpar o conteúdo exibido no terminal.

### Pausa na execução

```dart
sleep(Duration(seconds: 2));
```

Utilizada para criar pequenas pausas antes de limpar o terminal ou continuar a execução.

---

# 🧠 Conceitos de Dart utilizados

Durante o desenvolvimento deste projeto foram utilizados diversos conceitos fundamentais da linguagem Dart.

## Variáveis

```dart
int? input1;
dynamic nome, number;
```

Foram utilizadas variáveis para armazenar as opções escolhidas pelo usuário, nomes e números de telefone.

---

## Null Safety

O projeto utiliza recursos de null safety do Dart.

Exemplo:

```dart
int? input1;
```

O `?` indica que a variável pode possuir o valor `null`.

Também foi utilizado o operador `!`:

```dart
stdin.readLineSync()!;
```

Nesse caso, o programa informa ao Dart que o valor retornado não será `null`.

---

## Map

A estrutura principal utilizada para armazenar os contatos é:

```dart
Map<String, String> listaContato = {};
```

O `Map` trabalha com pares de:

```text
chave → valor
```

Neste projeto:

```text
Nome → Número
```

Exemplo:

```text
Kauã → 11999999999
João → 11888888888
Maria → 11777777777
```

---

## Funções

O projeto foi dividido em diversas funções para separar as responsabilidades da aplicação.

```dart
menu();
addContato();
listarContato();
updateContato();
removeContato();
buscarContato();
limparTerminal();
```

Essa divisão facilita a organização e manutenção do código.

---

## Estruturas condicionais

Foram utilizados `if` e `else if` para verificar qual opção foi escolhida pelo usuário.

```dart
if (input1 == 1) {
  addContato();
} else if (input1 == 2) {
  listarContato();
}
```

---

## Loop `while`

O menu principal utiliza um loop `while` para manter a aplicação funcionando até que o usuário escolha a opção de saída.

```dart
while (input1 != 6) {
  menu();
}
```

---

## `forEach()`

Utilizado para percorrer os contatos armazenados no `Map`.

```dart
listaContato.forEach(
  (key, value) => print("$key - $value"),
);
```

---

## `containsKey()`

Utilizado para verificar se determinado contato existe.

```dart
listaContato.containsKey(n2);
```

---

## `remove()`

Utilizado para remover contatos.

```dart
listaContato.remove(rm);
```

---

## `update()`

Utilizado para atualizar o número de um contato.

```dart
listaContato.update(
  nome,
  (number) => newNumber,
);
```

---

## `isEmpty`

Utilizado para verificar se o `Map` não possui contatos.

```dart
listaContato.isEmpty
```

---

## Conversão de tipos

A opção escolhida no menu é recebida como `String` pelo terminal e posteriormente convertida para `int`.

```dart
input1 = int.parse(
  stdin.readLineSync()!,
);
```

---

# 📂 Estrutura do projeto

Atualmente o projeto possui uma estrutura simples:

```text
Contact-List/
│
├── main.dart
└── README.md
```

### `main.dart`

É o arquivo principal da aplicação.

Nele estão:

* Menu
* Cadastro de contatos
* Listagem
* Atualização
* Remoção
* Busca
* Limpeza do terminal
* Loop principal da aplicação

---

# ▶️ Como executar

## 1. Instale o Dart SDK

Primeiro, verifique se o Dart está instalado:

```bash
dart --version
```

Caso o comando não seja encontrado, instale o Dart SDK antes de continuar.

---

## 2. Clone o repositório

```bash
git clone https://github.com/KauahsSantos/Contact-List.git
```

---

## 3. Entre na pasta

```bash
cd Contact-List
```

---

## 4. Execute o projeto

Utilizando:

```bash
dart run main.dart
```

ou:

```bash
dart main.dart
```

---

# 💻 Exemplo de execução

Ao iniciar o programa, será exibido:

```text
Lista De Contatos

1 - Adicionar contato
2 - Listar contato
3 - Atualizar contato
4 - Remover contato
5 - Buscar contato
6 - Sair contato

Escolha uma opção:
```

Ao escolher a opção de adicionar:

```text
Nome do Contato
Kauã

Digite o numero
11999999999
```

O contato será armazenado no `Map`:

```dart
{
  "Kauã": "11999999999"
}
```

---

# 💾 Armazenamento dos dados

Atualmente, os contatos são armazenados somente em memória utilizando:

```dart
Map<String, String> listaContato = {};
```

Isso significa que os dados **não são persistidos**.

Por exemplo:

```text
Executou o programa
      ↓
Adicionou contatos
      ↓
Fechou o programa
      ↓
Os contatos foram perdidos
```

Uma futura versão poderia utilizar:

* JSON
* Arquivo local
* SQLite
* Banco de dados
* API
* Cloud Database

---

# 🔄 Fluxo da aplicação

O funcionamento básico do programa pode ser representado assim:

```text
                 ┌───────────────┐
                 │ Inicia o app  │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │     Menu      │
                 └───────┬───────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   Adicionar          Listar           Buscar
        │                │                │
        └────────────────┼────────────────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
    Atualizar         Remover            Sair
        │                │                │
        └────────────────┴────────────────┘
                         │
                         ▼
                    Volta ao menu
```

---

# 🎯 Objetivo do projeto

O principal objetivo deste projeto é praticar os fundamentos da linguagem **Dart** através da criação de uma aplicação funcional.

Entre os conceitos praticados estão:

* Variáveis
* Tipos de dados
* Null Safety
* `Map`
* Funções
* Condicionais
* Loops
* Entrada e saída de dados
* Manipulação de coleções
* Métodos de `Map`
* Organização básica de código
* Execução de aplicações pelo terminal

---

# 🔮 Possíveis melhorias

Algumas funcionalidades podem ser adicionadas em versões futuras:

* [ ] Persistência dos contatos
* [ ] Salvamento em JSON
* [ ] Importação de contatos
* [ ] Validação de números
* [ ] Validação de nomes
* [ ] Impedir contatos duplicados
* [ ] Interface gráfica
* [ ] Versão Flutter
* [ ] Banco de dados local
* [ ] SQLite
* [ ] API para sincronização
* [ ] Pesquisa por parte do nome
* [ ] Organização dos contatos por categorias
* [ ] Favoritos
* [ ] Histórico de alterações

---

# 📚 O que este projeto demonstra

Mesmo sendo uma aplicação pequena, o projeto demonstra a utilização prática de conceitos importantes para quem está começando no desenvolvimento com Dart.

A aplicação trabalha com **entrada de dados**, **processamento**, **armazenamento temporário** e **saída de informações**, formando um pequeno sistema CRUD executado diretamente no terminal.

```text
Entrada
   ↓
Processamento
   ↓
Map<String, String>
   ↓
Manipulação dos dados
   ↓
Saída no terminal
```

---

# 👨‍💻 Autor

Desenvolvido por **Kauã Santos**.

GitHub:

**https://github.com/KauahsSantos**

---

# 📄 Licença

Este projeto foi desenvolvido para fins de **estudo e prática de programação com Dart**.

Sinta-se livre para estudar o código, modificar o projeto e utilizá-lo como base para seus próprios experimentos.
