# 📘 Documentação do Projeto - Desenvolvimento Web

[Planejamento do Projeto](./PMC.pdf)

---

## 🧾 Visão Geral

O aplicativo de resíduos sólidos introduz um sistema de gamificação e monetização para o usuário que deseja destinar seus resíduos corretamente, incentivando assim o descarte consciente e o engajamento da comunidade nesta causa.

O usuário gerador de resíduos se cadastrará na plataforma, inserindo um e-mail válido, seu nome, endereço, telefone, senha de acesso e horário disponível para o recolhimento do lixo - deve ser obrigatoriamente entre 6:00 AM e 8:00 PM.

Quando o usuário possuir resíduos que deseje descartar, deve selecionar a opção no aplicativo para agendar uma coleta no horário previamente cadastrado (pode estar sujeito a alteração).

Os parceiros do negócio serão os motoristas, que também precisará de cadastro na plataforma, incluindo seus dados pessoais como nome, CNH, data de nascimento, telefone para contato, e-mail e uma senha de acesso, além de informações sobre seu veículo de carga como modelo, ano, placa e capacidade de carga. Com o cadastro feito, o sistema emitirá um nada consta para habilitar a coleta dos resíduos. Os veículos serão equipados com balanças e containers para cada tipo de lixo.

O recolhimento se dará da seguinte forma: uma lista de endereços ordenada por hora daquele dia será mostrada na tela, o motorista selecionará quais endereços ele vai buscar os resíduos - evitando conflitos de horário - e deverá comparecer no local no horário escolhido, reunindo os resíduos, pesando-os e armazenando-os nos devidos containers.

Após a coleta e pesagem dos resíduos, o usuário que os descartou ganhará progresso nas missões de cada tipo de material presente em nossa plataforma e uma quantia de TrashCoin. TrashCoin é a moeda criada especialmente para o aplicativo, o usuário poderá trocá-las ao acessar a loja interna que oferece cupons variados.

O motorista, em posse dos resíduos coletados irá transportá-los para as empresas interessadas em obtê-los para reciclagem. Após a entrega, receberá uma quantia de TrashCoins que poderão ser convertidas em dinheiro posteriormente (para a retirada, a quantia de TrashCoins deverá ser maior que 15).

---

## ✅ Backlog

### 🧍‍♂️ Usuário Gerador de Resíduos

| ID   | História de Usuário                                                                                  |
|------|-------------------------------------------------------------------------------------------------------|
| U1   | Como usuário, quero me cadastrar com nome, e-mail, telefone, endereço, senha e horário de coleta, para agendar coletas. |
| U2   | Como usuário, quero ser obrigado a inserir horário entre 6:00 AM e 8:00 PM, para garantir coletas válidas. |
| U3   | Como usuário, quero acessar minha conta com e-mail e senha, para acompanhar coletas e saldo.          |
| U4   | Como usuário, quero agendar uma coleta de resíduos, para que o motorista venha buscá-los no horário.  |
| U5   | Como usuário, quero poder alterar meu horário de coleta cadastrado, para adaptar minha disponibilidade. |
| U6   | Como usuário, quero receber TrashCoins pelos resíduos descartados, para ser recompensado.             |
| U7   | Como usuário, quero acompanhar meu progresso em missões por tipo de resíduo, para me motivar a reciclar. |
| U8   | Como usuário, quero acessar uma loja interna para trocar TrashCoins por cupons variados.              |

---

### 🚛 Motorista (Parceiro de Coleta)

| ID   | História de Usuário                                                                                  |
|------|-------------------------------------------------------------------------------------------------------|
| M1   | Como motorista, quero me cadastrar com dados pessoais, CNH, e dados do veículo, para poder coletar resíduos. |
| M2   | Como motorista, quero que o sistema emita um "nada consta" após cadastro, para confirmar que estou apto. |
| M3   | Como motorista, quero acessar minha conta com e-mail e senha, para visualizar coletas e registrar ações. |
| M4   | Como motorista, quero visualizar uma lista de coletas ordenada por horário, para planejar minha rota.  |
| M5   | Como motorista, quero selecionar quais coletas vou realizar, para evitar conflitos de horário.         |
| M6   | Como motorista, quero registrar a coleta, pesando e separando os resíduos, para manter organização.    |
| M7   | Como motorista, quero receber TrashCoins pelas coletas realizadas e entregues, para ser recompensado.  |
| M8   | Como motorista, quero converter TrashCoins em dinheiro (acima de 15), para monetizar meu trabalho.     |

---

### 🛠️ Sistema/Admin

| ID   | História de Usuário                                                                                  |
|------|-------------------------------------------------------------------------------------------------------|
| S1   | Como sistema, quero validar o horário de coleta (6:00 AM - 8:00 PM), para evitar agendamentos inválidos. |
| S2   | Como sistema, quero emitir um "nada consta" após o cadastro do motorista, para habilitá-lo.            |
| S3   | Como sistema, quero calcular e atribuir TrashCoins com base no peso e tipo de resíduo, para recompensar usuários e motoristas. |
| S4   | Como sistema, quero atualizar o progresso de missões do usuário, para incentivá-lo a continuar reciclando. |
| S5   | Como sistema, quero manter uma loja interna com cupons, para que os usuários troquem suas TrashCoins. |

---

### 🏭 Empresa Recicladora 

| ID   | História de Usuário                                                                                  |
|------|-------------------------------------------------------------------------------------------------------|
| E1   | Como empresa recicladora, quero receber os resíduos já separados e pesados, para facilitar a reciclagem. |


---

## 🎨 Protótipo de Telas

Cada funcionalidade descrita no backlog possui ao menos uma tela representando sua interface esperada.

### 🖼️ Protótipo do Requisito HU-1

![Protótipo da tela de listagem de produtos](wireframe1.png)
**Figura 1**: Tela de listagem de produtos com imagem, nome e preço — correspondente à história de usuário HU-1.

---

## 🏗 Análise e Projeto 

O projeto  do sistema 

### Modelo 

![alt text](image-1.png)

### Esboço da arquitetura geral (cliente-servidor)


![alt text](image.png)


### Autorização  e Autenticação 
A autorização no Strapi (a partir do v4 e mantida no v5) é baseada em perfis de usuários (roles) e permissões atribuídas a esses perfis. Ela define o que cada usuário pode ou não pode fazer ao interagir com os endpoints da API.

1. Tipos de usuários
O Strapi tem dois contextos principais de usuários:

🔹 Usuários Autenticados
Criados via cadastro/login na API pública.

Associados a uma role do tipo “Authenticated” ou outra personalizada.

Usam token JWT para acesso autenticado.

🔸 Usuários Administrativos
Criados via painel de administração do Strapi.

Usam o Strapi Admin Panel.

Gerenciados separadamente e com permissões diferentes.


### Tecnologias a serem utilizadas 
Strapi, HTML, CSS, SQLITE....

---

### Telas do sistema

![alt text](tela1-1.png)
**Figura 2**: Tela de listagem de produtos com imagem, nome e preço — correspondente à história de usuário HU-1.


