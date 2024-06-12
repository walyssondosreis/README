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
- A resolução de conflito no git é baseada em um novo 'commit' ou seja identificado o conflito
é sugerido 3 opções: aceitar a alteração remota, aceitar a alteração local ou mesclar ambos, após feito
isso salve os arquivos e faça um novo commit. Submeta o commit para o repositorio do projeto com 'push'
e ai os conflitos estarão resolvidos.

### Configurando projeto
~~~bash
git clone URL
git status
git add . // Adiciona todos os arquivos alterados para ser commmitados.

git push origin main // Publica para o repositorio remoto
git pull origin main // Baixa alterações do repositorio remoto

#Sobre repositorios
- O repositorio é publico apenas para leitura, para colaboração mesmo sendo public devo adicionar a conta da pessoa no projeto
|-> Repositorio > Settings > Collaborators > Add People

# Configurar GIT no linux

git config --global user.name "Walysson dos Reis"
git config --global user.email walyxxxx@xxxxx.com
git config --global user.signingKey 'senha'
git config --global credential.helper store

# Subir um novo projeto do PC para o GitHub

echo "# nome-repositorio" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
/*-------------------------------------------
// É recomentado vincular o repositório remoto via SSH e não HTTPS
git remote add origin git@github.com:walyssondosreis/meu-projeto.git
// Se o PC não estiver vinculado a sua conta GitHub será necessario vincular através de uma chave SSH:
No GitHub: Profile >> Settings >> SSH and GPG keys >> New SSH key
Title : Qualquer titulo 
Key type: Authentiation key
Key: ** Chave SSH gerada no dispositivo **
- Verifique se já existe alguma chave SSH no dispositivo local em ~/.ssh.
- Se não gere nova chave com: ssh-keygen -t ed25519 -C "your_email@example.com"
- Será perguntado sobre onde gerar o arquivo e se você quer definir uma senha ,
caso definido essa senha toda vez que fizer pull sera solicitado a senha.
- Abra a chave publica gerada em ~/.ssh e copie o seu valor e cole no GitHub. 
-------------------------------------------*/
git push -u origin main

# Comando Remote
// Adiciona um repositorio remoto
git remote add origin url // Pode ser origin ou qualquer outro apelido que faça sentido para o projeto.
// Lista repositorios remotos associados ao projeto
git remote -v
// Remove um repositório remoto
git remote remove origin
// Atualiza a url de um repositorio
git remote set-url origin nova_url
// Renomeia um repositorio remoto
git remote rename origin novo-origin

~~~~
### .gitignore
~~~bash
.gitignore

Adicionar pastas e arquivos para serem ignorados no commit

Site que cria .gitignore padrão para principais linguagens e frameworks.
https://www.toptal.com/developers/gitignore
~~~
### Github Gist
~~~bash
A ferramenta gist do GitHub é feita para que seja possível 
compartilhar trechos de codigos, ou mesmo armazenar de modo privado.
~~~
--------
## Referências  
https://docs.github.com/pt  
https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent  
https://www.toptal.com/developers/gitignore  

