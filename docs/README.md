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

| ID    | Prioridade | História de Usuário                                                                 |
|-------|------------|--------------------------------------------------------------------------------------|
| HU-1  | 1️⃣         | **No papel de cliente**, desejo **visualizar uma lista de produtos com imagem e preço**, para poder escolher o que desejo comprar. |
| HU-2  | 2️⃣         | **No papel de cliente**, desejo **filtrar os produtos por categoria**, para encontrar mais rapidamente o que procuro. |
| HU-3  | 3️⃣         | **No papel de cliente**, desejo **adicionar um produto ao carrinho**, para organizar minha compra antes de finalizar. |
| HU-4  | 4️⃣         | **No papel de cliente**, desejo **visualizar os itens no meu carrinho com totais**, para acompanhar o valor da compra. |
| HU-5  | 5️⃣         | **No papel de cliente**, desejo **remover ou alterar a quantidade de itens no carrinho**, para ajustar minha compra. |
| HU-6  | 6️⃣         | **No papel de cliente**, desejo **finalizar o pedido com um clique**, para concluir minha compra com rapidez. |
| HU-7  | 7️⃣         | **No papel de cliente**, desejo **ver uma confirmação visual do pedido após finalizar**, para ter certeza que deu tudo certo. |
| HU-8  | 8️⃣         | **No papel de cliente**, desejo **me autenticar com login e senha**, para acessar meu histórico de pedidos e carrinho. |
| HU-9  | 9️⃣         | **No papel de cliente**, desejo **visualizar o histórico de pedidos realizados**, para acompanhar minhas compras anteriores. |
| HU-10 | 🔟         | **No papel de administrador**, desejo **visualizar todos os pedidos realizados**, para acompanhar e organizar a entrega. |

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


