# **GIT**
<div>
<img src="http://git-scm.com/images/logos/downloads/Git-Logo-1788C.png" alt="logoJS" width="50px"/> 
</div>

*Autor: Walysson dos Reis*

----------------------------------------------
*Manual de consulta rápida dos conceitos e principais comandos.*

---------------------
### Sobre Commits
~~~bash
git commit -m "Minhas Alterações"
git log // Mostra historico dos commits

// O git revert ele desfaz um commit porém não apaga ele cria um novo commit desfazendo essas alterações
git revert id_commit

** A resolução de conflito no git é baseada em um novo 'commit' ou seja identificado o conflito
é sugerido 3 opções: aceitar a alteração remota, aceitar a alteração local ou mesclar ambos, após feito
isso salve os arquivos e faça um novo commit. Submeta o commit para o repositorio do projeto com 'push'
e ai os conflitos estarão resolvidos.

// Apaga um commit -- IMPORTANTE utilizar apanas caso commit não tenha sido enviado via pro repositório 'push'
git reset --hard id_commit_ANTERIOR // Importante passar o id do commit anterior não do que eu quero 'apagar'
// a opção --hard faz com seja desfeito não só o commit como também as alterações nos arquivos.

# Sugestão para mensagem de commit
- Mantenha a mensagem curta e concisa: No máximo 72 char , se nessario descrição adicional pule uma linha.
- Uso de verbo no infinitivo: Utilizar como 'adicionar titulo pagina inicial', 'corrigir funcionalidade ...','atualizar'.
- Evite detalhes técnicos: Esses detalhes devem ser adionados em comentários no codigo ou na documentação.
*Evitar realizar commits muito pequenos ou muito grandes*

// Adciona um co-autor em um commit :
$ git commit -m "Adicionar nova funcionalidade.
>
>
Co-authored-by: NOME <nome@email.com>
Co-authored-by: OUTRO-NOME <outro@email.com>"


// Altera um commit arquivos ou apenas mensagem:

git commit --amend -m "Trocando mensagem do commit"


Estes comandos só devem ser aplicados a commits que NÃO foram enviados ao repositório remoto.
A integridade do histórico de commits é fundamental.
O historico de commits é a representação precisa do progresso do projeto ao longo do tempo .
~~~

~~~git
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


--------
## Referências  
https://docs.github.com/pt  
https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
