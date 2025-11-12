# PROJETO 2 - MODELAGEM DE SOFTWARE ORIENTADO A OBJETOS

# Diagrama de Casos de Uso

<img width="789" height="524" alt="Casos_De_Uso drawio (2)" src="https://github.com/user-attachments/assets/c89b9a80-e502-4ed3-88fc-2a679f3c7d54" />



| **Identificação** | **UC01 – Cadastrar Gerente**|
|-------------------|-----------------------------|
| **Função** |O processo de cadastro de um usuário gerente (controlador) no sistema de controle de elevadores.|
| **Atores** |Usuário Master|
| **Pré-condição** | O Usuário Master deve estar autenticado no sistema.|
| **Pós-condição** | O gerente é cadastrado e pode acessar as funções de gerenciamento de elevadores.|
| **Fluxo principal** | 1 - O Usuário Master acessa o módulo de gerenciamento de usuários.<br>2 - O sistema solicita as informações de cadastro (nome, login, senha, e-mail, nível de autorização).<br>3 - O Usuário Master insere os dados solicitados.<br>4 - O sistema valida as informações e armazena o novo usuário gerente.<br>5- O sistema confirma a criação do cadastro.|
| **Fluxo Alternativo** | Não há.|
| **Fluxo de Exceção** | 1 - Falha ao salvar os dados no banco de dados.<br>2 - O sistema exibe mensagem de erro informando falha no cadastro.|
<br>
<br>

| **Identificação** | **UC02 – Cadastrar Cliente VIP**|
|-------------------|-----------------------------|
| **Função** |Serve para cadastro de um cliente VIP, autorizando seu acesso aos andares restritos através de reconhecimento facial|
| **Atores** |Usuário Master|
| **Pré-condição** | O Usuário Master deve estar autenticado no sistema.|
| **Pós-condição** | O cliente VIP é cadastrado com seus dados e imagem facial associados.|
| **Fluxo principal** | 1 - O Usuário Master acessa o módulo de cadastro de clientes VIP.<br>2 - O sistema solicita as informações de cadastro (nome, documento, e-mail, imagem facial).<br>3 - O Usuário Master insere os dados e realiza a captura facial.<br>4 - O sistema valida e armazena os dados do cliente VIP.<br>5 - O sistema confirma o cadastro.|
| **Fluxo Alternativo** | Caso a captura facial falhe, o sistema solicita nova tentativa.|
| **Fluxo de Exceção** | 1 - Falha na comunicação com o banco de dados.<br>2 - O sistema exibe mensagem de erro informando falha no cadastro.|
<br>
<br>

| **Identificação** | **UC03 – Gerenciar Elevadores**|
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

| **Identificação** | **UC04 – Usar Elevador**|
|-------------------|-----------------------------|
| **Função** |Utilização do elevador pelos clientes e usuários autorizados.|
| **Atores** |Clientes, Usuário Controlador|
| **Pré-condição** |O sistema deve estar operacional e o elevador disponível.|
| **Pós-condição** | O usuário chega ao andar desejado.|
| **Fluxo principal** | 1 - O usuário chama o elevador por meio da botoeira externa.<br>2 - O sistema identifica o elevador mais próximo e envia-o ao andar solicitado.<br>3 - O usuário entra e seleciona o andar de destino.<br>4 - O sistema move o elevador e exibe o andar atual e os próximos destinos.<br>5 - O elevador para no andar selecionado e abre as portas.|
| **Fluxo Alternativo** | 1 - Caso o andar seja VIP, o sistema solicita autenticação facial antes de prosseguir.<br>2 - Se a autenticação falhar, o acesso ao andar é negado.|
| **Fluxo de Exceção** | 1 - O elevador está em manutenção.<br>2 - O sistema exibe mensagem informando indisponibilidade do serviço.|
<br> 
<br>

| **Identificação** | **UC05 – Prevenção de Segurança**|
|-------------------|-----------------------------|
| **Função** |O comportamento do sistema durante situações de incêndio ou emergência.|
| **Atores** |Sistema de Segurança, Usuário Controlador|
| **Pré-condição** |O sistema de segurança deve estar integrado ao sistema de controle de elevadores.|
| **Pós-condição** |Todos os elevadores são posicionados conforme o tipo de emergência e ficam parados até liberação.|
| **Fluxo principal** | 1 - O Sistema de Segurança detecta uma emergência e envia sinal ao sistema de elevadores.<br>2 - O sistema identifica o tipo de emergência (incêndio ou outra).<br>3 - Em caso de incêndio, todos os elevadores descem até o térreo e abrem as portas.<br>4 - Em outras emergências, os elevadores param no andar mais próximo e abrem as portas.<br>5 - Após evacuação, os elevadores são bloqueados até liberação manual.|
| **Fluxo Alternativo** | Caso o sistema automático falhe, o Usuário Controlador aciona o modo de emergência manualmente.|
| **Fluxo de Exceção** | 1 - Falha na comunicação com o sistema de segurança.<br>2 - O sistema exibe mensagem de alerta e aguarda comando manual.|

# Diagrama de Classe

<img width="1211" height="641" alt="image" src="https://github.com/user-attachments/assets/f4d20d20-4a38-438f-a346-e32d7cdf84c6" />
