# **GIT**
<div>
<img src="http://git-scm.com/images/logos/downloads/Git-Logo-1788C.png" alt="logoJS" width="50px"/> 
</div>

*Autor: Walysson dos Reis*

----------------------------------------------
*Manual de consulta rápida dos conceitos e principais comandos.*

---------------------
~~~git
git clone URL
git status
git add . // Adiciona todos os arquivos alterados para ser commmitados.
git commit -m "Minhas Alterações"
git push // PUBLICA DO PC PARA O SERVIDOR
git pull // BAIXA DO SERVIDOR PARA O PC


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
