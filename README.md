# 🐙 DIO | Git e GitHub 
> Um guia rápido para os comandos essenciais do dia a dia.

---

## 🌱 1. Configuração & Início
Comandos para preparar o terreno.

| Comando | O que faz |
| :--- | :--- |
| `git init` | Transforma a pasta atual em um repositório Git. |
| `git clone <url>` | Baixa um repositório completo (ex: GitHub). |
| `git config --global user.name "Nome"` | Define seu nome de usuário. |
| `git config --global user.email "Email"` | Define seu email. |

---

## 🔨 2. Fluxo de Trabalho (Dia a Dia)
A rotina básica: **Modificar ➡ Preparar ➡ Salvar**.

| Comando | O que faz |
| :--- | :--- |
| `git status` | **Sempre use.** Mostra o que foi alterado. |
| `git add .` | Adiciona **todos** os arquivos ao *staging* (preparação). |
| `git add <arquivo>` | Adiciona apenas um arquivo específico. |
| `git commit -m "msg"` | Salva a versão no histórico com uma mensagem. |
| `git log --oneline` | Mostra o histórico de forma resumida. |

---

## 🌿 3. Branches (Ramificações)
Para trabalhar em novas funcionalidades sem quebrar o código principal.

| Ação | Comando |
| :--- | :--- |
| **Listar** | `git branch` |
| **Criar** | `git branch <nome>` |
| **Trocar** | `git switch <nome>` _(ou `git checkout`)_ |
| **Criar & Trocar** | `git checkout -b <nome>` |
| **Deletar** | `git branch -d <nome>` |
| **Juntar (Merge)** | `git merge <nome>` _(estando na branch destino)_ |

---

## 🚀 4. Sincronização (Remoto)
Conectando com a nuvem (GitHub/GitLab).

* 📥 **Baixar:** `git pull origin main` (Traz atualizações e junta)
* 📤 **Enviar:** `git push origin main` (Envia seus commits)
* 👀 **Espiar:** `git fetch` (Baixa atualizações mas não aplica ao código)

---

## ⏪ 5. Emergências (Undo)
_Use com cautela!_

| Situação | Comando |
| :--- | :--- |
| Mudei um arquivo mas quero desfazer | `git checkout -- <arquivo>` |
| Fiz o commit mas quero desfazer (manter edições) | `git reset --soft HEAD~1` |
| Quero apagar o último commit e as edições | `git reset --hard HEAD~1` |
| Guardar mudanças num "bolso" temporário | `git stash` |
| Recuperar mudanças do "bolso" | `git stash pop` |
| [Documentação Git](https://git-scm.com/docs)
| [Documentação GitHub](https://docs.github.com/pt)
| [Crie Readme](https://readme.so/pt/editor)

