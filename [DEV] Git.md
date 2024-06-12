# **GIT**
<div>
<img src="http://git-scm.com/images/logos/downloads/Git-Logo-1788C.png" alt="logoJS" width="50px"/> 
</div>

*Autor: Walysson dos Reis*

----------------------------------------------
*Manual de consulta rápida dos conceitos e principais comandos.*

---------------------

### Sobre Commits
- O historico de commits é a representação precisa do progresso do projeto ao longo do tempo, portanto a integridade desse histórico é fundamental.
- O comando 'reset' NÃO deve ser utilizado para commits que já foram enviados para o repositório remoto, isso pode causar problemas no projeto.
- Evite realizar commits muito pequenos ou muito grandes, isso irá facilitar a manipulação e leitura do histórico de commits.
- Sugestão para mensagem de commit:
  - Mantenha a mensagem curta e concisa: No máximo 72 caractéres , se nessário descrição adicional pule uma linha.
  - Uso de verbo no infinitivo: Utilizar verbos como 'adicionar...', 'corrigir ...','atualizar...' na composição da mensagem.
  - Evite detalhes técnicos: Detalhes técnicos devem ser adicionados em comentários no codigo ou na documentação do projeto.

~~~bash
# Efetua commit de arquivos.
git commit -m "Minhas Alterações"
# Mostra histórico de commits.
git log
# Desfaz um commit criando um automaticamente um novo de reversão.
git revert id_commit
# Apaga um commit. Importante passar o id do commit anterior e não do qual quero 'apagar'.
# A opção '--hard' faz com que seja desfeito não só o commit como também as alterações nos arquivos modificados.
git reset --hard id_commit_ANTERIOR
# Altera arquivos de um commit ou mesmo só a mensagem de um commit:
git commit --amend -m "Trocando mensagem do commit"
# Adiciona co-autores em commit :
$ git commit -m "Adicionar nova funcionalidade.
>
>
Co-authored-by: NOME <nome@email.com>
Co-authored-by: OUTRO-NOME <outro@email.com>"
~~~
### Sobre conflitos
- A resolução de conflito no git é baseada em um novo commit ou seja identificado o conflito é sugerido 3 opções: aceitar a alteração remota, aceitar a alteração local ou mesclar ambos. Após resolvido conflito salve os arquivos e faça um novo commit. Submeta o commit para o repositorio remoto, resolvendo assim o conflito.

### Sobre repositórios
- Repositórios mesmo sendo públicos não é permitido alteração, ou seja são somente leitura.
- Para colaboração em um projeto publico ou privado deve adicionar o usuário git colocaborador ao projeto em : Repositorio > Settings > Collaborators > Add People.
~~~bash
# Baixa versão do projeto
git clone URL
# Verifica status do projeto
git status
# Adiciona arquivos para serem commitados
git add .
# Envia commits para o repositório remoto
git push origin main
# Envia os commits ao repositorio remoto.
# A opção -u define que o branch padrão é o origin, podendo assim nos proximos comando utilizar apenas git push.
git push -u origin main
# Baixa commits do repositório remoto
git pull origin main
# Inicializa um diretório local para o git
git init
# Define o branch que principal 
git branch -M main
# Adiciona um repositório remoto
git remote add origin git@github.com:walyssondosreis/meu-projeto.git
# Adiciona um repositorio remoto. Pode ser origin ou qualquer outro apelido que faça sentido para o projeto.
git remote add origin url  
# Lista repositorios remotos associados ao projeto
git remote -v
# Remove um repositório remoto
git remote remove origin
# Atualiza a url de um repositorio
git remote set-url origin nova_url
# Renomeia um repositorio remoto
git remote rename origin novo-origin
~~~
### Sobre configurações
- É recomendado vincular o repositório remoto via SSH em vez de HTTPS.
- Se o PC não estiver vinculado a sua conta GitHub será necessario vincular através de uma chave SSH.
- Verifique se já existe alguma chave SSH no dispositivo local em ~/.ssh.
- Se não gere nova chave com: ssh-keygen -t ed25519 -C "your_email@example.com"
- Será perguntado sobre onde gerar o arquivo e se você quer definir uma senha, caso definido senha esta será solicitada sempre que for acionado o repositorio remoto.
- Abra a chave publica gerada em ~/.ssh e copie o seu valor e cole no GitHub.
- No GitHub: Profile >> Settings >> SSH and GPG keys >> New SSH key
  - Title : Qualquer titulo 
  - Key type: Authentiation key
  - Key: ** Chave SSH gerada no dispositivo **
~~~bash
# Configura o nome de usuário de forma global no dispositivo
git config --global user.name "Walysson dos Reis"
# Configura o email de usuário de forma global no dispositivo
git config --global user.email walyxxxx@xxxxx.com
# Configura para que seja armazenada as credenciais no dispositivo
git config --global credential.helper store
~~~
### .gitignore
- O arquivo .gitignore serve para adicionar pastas e arquivos para serem ignorados no commit.
- Este site fornece o .gitignore padrão para as principais linguagens e frameworks: https://www.toptal.com/developers/gitignore

### Github Gist
- A ferramenta gist do GitHub é feita para que seja possível compartilhar trechos de codigos, ou mesmo armazenar de modo privado.

--------
## Referências  
https://docs.github.com/pt  
https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent  
https://www.toptal.com/developers/gitignore  

