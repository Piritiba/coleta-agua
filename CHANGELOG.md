# Histórico de versões — App Coleta de Água (Firebase)

A versão atual aparece no rodapé da tela **Equipe** e na tela de login.

## v1.7 — 19/11/2026
- **Cronograma no formato do documento da Humaniza:** tabela com Periodicidade, Tipo de coleta, Exames e os 12 meses (Jan/27 … Dez/27), mostrando a quantidade de pontos e, quando for o caso, os hospitais entre parênteses — ex.: "5 (HJV e HC)", "5 (demais hospitais)". Abaixo, o quantitativo de equipamentos e as OBS, como no documento.
- Botão **"Criar a partir do modelo Humaniza"** (administrador): monta o cronograma com as 3 linhas do documento 2027 (microbiológica mensal nas osmoses, físico-químico semestral nas osmoses e microbiológica anual do dialisato). Também é possível copiar do ano anterior ou criar em branco.
- Cada mês da tabela gera automaticamente as coletas de cada hospital; tocar no mês mostra os hospitais e o andamento (✓ todas coletadas, ● em andamento, ! atrasada).
- Administrador edita linhas (periodicidade, tipo, exames, equipamento), cada mês (todos, somente alguns hospitais, ou "demais hospitais"; quantidade de pontos; texto entre parênteses), título e OBS.
- No Painel do mês, cada coleta mostra o tipo de coleta e o número de pontos.
- **Regras do Firebase mudaram:** é preciso colar o novo `firestore.rules`.

## v1.6 — 19/11/2026
- **Só administradores alteram cadastros.** Usuários comuns não editam mais nem o próprio cadastro: a opção "Meu cadastro" e o botão "Editar" da Equipe aparecem só para administradores. Para corrigir dados, o usuário fala com um administrador.
- Continua só de administradores: cadastro de usuários, hospitais, máquinas e cronograma (criar/excluir coletas).
- Usuários comuns continuam atualizando apenas o **andamento das coletas** (status, data, responsável, resultado, laudo, observações).
- Ajuste: ao trocar de aba, janelas abertas se fecham sozinhas.
- **Regras do Firebase mudaram:** é preciso colar o novo `firestore.rules` (Firestore → Regras → Publicar).

## v1.5 — 19/11/2026
- **Correção:** usuário que já existia (de versões anteriores) e foi cadastrado de novo pelo administrador agora recebe a **função, o hospital e a permissão** definidos no cadastro. Antes, ficava com os dados antigos (ex.: "Gestão" e sem hospital).
- Na aba **Hospitais**, qualquer usuário pode tocar no hospital para ver os detalhes: **máquinas de hemodiálise e de osmose** (marca, série, ano), pontos de coleta e equipe. Administradores também têm os botões "Editar hospital" e "Gerenciar máquinas".
- A mensagem "Erro ao carregar os dados" agora diz **qual lista** falhou e lembra de publicar as regras da versão.
- **Regras do Firebase mudaram:** é preciso colar o novo `firestore.rules` (Firestore → Regras → Publicar).

## v1.4 — 19/11/2026
- Novo **Cadastro de máquinas** no módulo Admin, com abas **Hemodiálise** e **Osmose**.
- Cada máquina tem: marca, código de série, ano de compra, hospital onde está e observações. O app avisa se o código de série for repetido.
- Filtro por hospital, e as máquinas aparecem agrupadas por hospital.
- Na aba Hospitais, cada hospital mostra quantas máquinas de hemodiálise e de osmose tem.
- **Regras do Firebase mudaram:** é preciso colar o novo `firestore.rules` (Firestore → Regras → Publicar).

## v1.3 — 19/11/2026
- Ao tocar no **nome do usuário** (canto superior direito), abre um menu com: Meu cadastro, Equipe e **Sair do sistema**.
- Só é preciso atualizar o `index.html` no Netlify. **Regras do Firebase não mudaram.**

## v1.2.1 — 19/11/2026
- Configuração do projeto Firebase **coleta-de-agua** e do administrador (gustavo.s.almeida@gmail.com) já preenchida no index.html e no firestore.rules.
- Sem mudanças de funcionamento.

## v1.2 — 19/11/2026
- Nova aba **Admin**, visível só para administradores: cadastro de usuários (pelo e-mail pessoal, com permissão Usuário ou Administrador), cadastro de hospitais e geração do cronograma.
- Só entra quem foi cadastrado por um administrador; outros e-mails veem "Acesso não liberado".
- Usuários comuns só atualizam o andamento das coletas (status, data, responsável, resultado, laudo).
- Regras do Firestore atualizadas (**é preciso colar o novo firestore.rules**).
- Número da versão exibido no app.

## v1.1 — 19/11/2026
- Botão **Entrar com Google** (é preciso ativar o provedor Google no Firebase).

## v1.0 — 19/11/2026
- Primeira versão com login próprio por e-mail e senha (Firebase Authentication + Firestore).
- Painel do mês, Cronograma, Hospitais e Equipe; cadastro com aprovação do administrador.
