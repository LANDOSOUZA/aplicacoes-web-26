1. Clonar o repositório do professor

git clone https://github.com/danielvieira95/AplicacoesWeb_2026.git

2. Entrar na pasta clonada

cd AplicacoesWeb_2026

3. Confirmar o remoto conectado

git remote -v

git config --global user.name "LANDOSOUZA"
git config --global user.email "lando-souza@hotmail.com"

4. Trocar o remoto para o seu repositório novo (depois de criar/recriar o aplicacoes-web-26 vazio no GitHub)

git remote set-url origin https://github.com/LANDOSOUZA/aplicacoes-web-26.git

5. Confirmar a troca

git remote -v

6. Verificar a branch atual

git branch

7. Renomear a branch de master para main

git branch -M main

8. Enviar tudo para o seu repositório

git push -u origin main

9. Verificar status

git status

Extra — se der erro de permissão (403) por credencial errada salva no Windows:

git credential-manager github logout

(depois tentar o git push de novo e logar com a conta correta)

Pendente para depois do recreio — atualizar com as mudanças do professor:

git pull origin main


---------------------------------------------------------------------------------------
Como você já trocou o origin para o seu repositório, o Git não tem mais conexão direta com o repositório do professor. Pra puxar as atualizações dele, o jeito certo é adicionar o repositório dele como um segundo remoto (chamado, por convenção, upstream):

1. Adicionar o repositório do professor como remoto extra

git remote add upstream https://github.com/danielvieira95/AplicacoesWeb_2026.git

minha main - professor master

2. Confirmar que agora tem os dois remotos

git remote -v

Deve aparecer origin (o seu) e upstream (o do professor).

3. Buscar as atualizações do professor

git fetch upstream

4. Mesclar as atualizações na sua branch main

git merge upstream/master --allow-unrelated-histories

5. Se não der conflito, enviar pro seu repositório

git push origin main

-----------------------------------------------------------------------------------
Comandos para commit

A sequência padrão pra fechar a aula é:

1. Ver o que mudou (opcional, mas ajuda a conferir)

git status

2. Adicionar todos os arquivos alterados

git add .

3. Fazer o commit com uma mensagem descritiva

git commit -m "Descrição do que foi feito hoje"

(por exemplo: "README criado e sincronização com repositório do professor")

4. Enviar pro seu repositório no GitHub

git push origin main

---------------------------------------------------------------------------------