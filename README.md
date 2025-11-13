# PROJETO 2 - MODELAGEM DE SOFTWARE ORIENTADO A OBJETOS

# Diagrama de Casos de Uso


<img width="789" height="524" alt="Casos_De_Uso drawio (3)" src="https://github.com/user-attachments/assets/e06d284c-b512-433c-9f69-5e187d877754" />



| **Identificação** | **UC01 – Cadastrar Controlador**|
|-------------------|-----------------------------|
| **Função** |O processo de cadastro de um usuário controlador no sistema de controle de elevadores.|
| **Atores** |Usuário Master|
| **Pré-condição** | O Usuário Master deve estar autenticado no sistema.|
| **Pós-condição** | O controlador é cadastrado e pode acessar as funções de gerenciamento de elevadores.|
| **Fluxo principal** | 1 - O Usuário Master acessa o módulo de gerenciamento de usuários.<br>2 - O sistema solicita as informações de cadastro (nome, login, senha, e-mail, nível de autorização).<br>3 - O Usuário Master insere os dados solicitados.<br>4 - O sistema valida as informações e armazena o novo usuário gerente.<br>5- O sistema confirma a criação do cadastro.|
| **Fluxo Alternativo** | Não há.|
| **Fluxo de Exceção** | 1 - Falha ao salvar os dados no banco de dados.<br>2 - O sistema exibe mensagem de erro informando falha no cadastro.|
<br>
<br>


| **Identificação** | **UC02 – Gerenciar Elevadores**|
|-------------------|-----------------------------|
| **Função** |Configuração e monitoramento dos elevadores pelo Usuário Controlador.|
| **Atores** |Usuário Controlador|
| **Pré-condição** |O Usuário Controlador deve estar autenticado no sistema.|
| **Pós-condição** | As configurações e status dos elevadores são atualizados e salvos.|
| **Fluxo principal** | 1 - O Usuário Controlador acessa o painel de gerenciamento de elevadores.<br>2 - O sistema exibe a lista de elevadores e suas configurações.<br>3 - O Usuário Controlador seleciona um elevador para visualizar ou alterar parâmetros (ex: andares atendidos, modo de operação).<br>4 - O sistema valida e salva as alterações realizadas.<br>5 - O sistema registra o evento no log de auditoria.|
| **Fluxo Alternativo** | O Usuário Controlador opta por apenas visualizar as informações sem realizar alterações.|
| **Fluxo de Exceção** | 1 - Falha na comunicação com os elevadores.<br>2 - O sistema exibe mensagem de erro e aborta a operação.|
<br>
<br>

| **Identificação** | **UC03 – Usar Elevador**|
|-------------------|-----------------------------|
| **Função** |Utilização do elevador pelos clientes e usuários autorizados.|
| **Atores** |Clientes, Usuário Controlador|
| **Pré-condição** |O sistema deve estar operacional e o elevador disponível.|
| **Pós-condição** | O usuário chega ao andar desejado.|
| **Fluxo principal** | 1 - O usuário chama o elevador por meio da botoeira externa.<br>2 - O sistema identifica o elevador mais próximo e envia-o ao andar solicitado.<br>3 - O usuário entra e seleciona o andar de destino.<br>4 - O sistema move o elevador e exibe o andar atual e os próximos destinos.<br>5 - O elevador para no andar selecionado e abre as portas.|
| **Fluxo Alternativo** | 1 - Caso o elevador já esteja em movimento atendendo outra chamada, o sistema adiciona o novo destino à fila de paradas.<br>2 - Se houver múltiplas chamadas no mesmo andar, o sistema prioriza a solicitação de acordo com a direção (subida ou descida).|
| **Fluxo de Exceção** | 1 - O elevador está em manutenção.<br>2 - O sistema exibe mensagem informando indisponibilidade do serviço.|
<br> 
<br>

| **Identificação** | **UC04 – Prevenção de Segurança**|
|-------------------|-----------------------------|
| **Função** |O comportamento do sistema durante situações de incêndio ou emergência.|
| **Atores** |Sistema de Segurança, Usuário Controlador|
| **Pré-condição** |O sistema de segurança deve estar integrado ao sistema de controle de elevadores.|
| **Pós-condição** |Todos os elevadores são posicionados conforme o tipo de emergência e ficam parados até liberação.|
| **Fluxo principal** | 1 - O Sistema de Segurança detecta uma emergência e envia sinal ao sistema de elevadores.<br>2 - O sistema identifica o tipo de emergência (incêndio ou outra).<br>3 - Em caso de incêndio, todos os elevadores descem até o térreo e abrem as portas.<br>4 - Em outras emergências, os elevadores param no andar mais próximo e abrem as portas.<br>5 - Após evacuação, os elevadores são bloqueados até liberação manual.|
| **Fluxo Alternativo** | Caso o sistema automático falhe, o Usuário Controlador aciona o modo de emergência manualmente.|
| **Fluxo de Exceção** | 1 - Falha na comunicação com o sistema de segurança.<br>2 - O sistema exibe mensagem de alerta e aguarda comando manual.|

# Diagrama de Classe

<img width="1097" height="1672" alt="Untitled diagram-2025-11-12-234001" src="https://github.com/user-attachments/assets/39717c29-d7e9-4bf0-85f8-4f959ec214bc" />

# Diagrama de Sequência

**UC01 – Cadastrar Controlador**

<img width="613" height="460" alt="image" src="https://github.com/user-attachments/assets/bef9b2e7-48a3-4db7-b92a-e80bed7d1696" />

**UC02 – Gerenciar Elevadores**

<img width="600" height="396" alt="image" src="https://github.com/user-attachments/assets/221c8d2c-8cf7-4336-aeeb-66bd420d1f98" />

**UC03 – Usar Elevador**

<img width="561" height="514" alt="image" src="https://github.com/user-attachments/assets/eb660a17-4c11-4d14-97a4-1584f07be46b" />

**UC04 – Prevenção de Segurança**

<img width="524" height="345" alt="image" src="https://github.com/user-attachments/assets/07611172-98f3-4d64-b438-42f29bd00720" />


# Diagrama de Atividade 

## Prevenção de segurança

<img width="803" height="420" alt="image" src="https://github.com/user-attachments/assets/f80b6516-217c-4006-afcf-4099841eb24e" />

## Controlador de Usuário

<img width="1051" height="669" alt="image" src="https://github.com/user-attachments/assets/dc236a00-841d-4b97-bd8b-b2f05795ff48" />

# Diagrama de Estados

## Cadastrar Controlador UC01

<img width="1043" height="161" alt="image" src="https://github.com/user-attachments/assets/93639c0c-d5f6-4cc0-826c-fd2210078971" />

## Gerenciar Elevadores UC02 

<img width="1135" height="196" alt="image" src="https://github.com/user-attachments/assets/82e9dc44-eaf1-40d5-8e0e-e7274202053c" />

## Usar Elevador UC03

<img width="1077" height="180" alt="image" src="https://github.com/user-attachments/assets/cee33ff1-1770-4c5b-a911-49759a7fa9c2" />

## Prevenção de Segurança UC04

<img width="1070" height="204" alt="image" src="https://github.com/user-attachments/assets/f549d564-69ff-4920-ab9a-1a75c9fabd3c" />

# Diagramas de Componentes e Implantação

<img width="481" height="421" alt="Diagrama sem nome drawio" src="https://github.com/user-attachments/assets/64024cb6-3d95-4a8c-bf71-b19df731d50c" />


