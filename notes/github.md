## GitHub

O **GitHub** é uma plataforma de hospedagem de código que utiliza o **Git** como sistema de controle de versão. Ele permite que desenvolvedores colaborem em projetos de software, compartilhem código, rastreiem alterações, gerenciem issues e muito mais. GitHub também permite o uso de **repositórios remotos** para sincronizar código entre vários dispositivos e desenvolvedores.

### Configurar uma SSH no GitHub

Para uma conexão segura entre o seu computador e o GitHub, a autenticação SSH é recomendada. Isso elimina a necessidade de inserir suas credenciais a cada push/pull.

### Repositório Remoto

Um **repositório remoto** é uma cópia do seu projeto hospedada em uma plataforma como o GitHub, permitindo que você colabore e sincronize seu código. Para trabalhar com ele:

- **Clonar um repositório remoto**:
  - Clonar traz uma cópia do repositório para sua máquina local:
    ```bash
    git clone git@github.com:usuario/repo.git
    ```
  - Substitua `usuario/repo.git` pelo endereço SSH do seu repositório.

- **Adicionar um repositório remoto**:
  - Se você já tiver um repositório local, adicione um repositório remoto para sincronizar:
    ```bash
    git remote add origin git@github.com:usuario/repo.git
    ```

---

### Fetch

O comando `git fetch` busca todas as alterações do repositório remoto, mas não as integra ao seu projeto local. Ele é útil para ver o que mudou no servidor antes de fazer qualquer modificação local.

```bash
git fetch origin
```

- Isso busca as alterações do repositório remoto `origin` (geralmente o padrão) e atualiza suas referências locais.

---

### Pull

O `git pull` é uma combinação de `git fetch` e `git merge`. Ele busca as alterações no repositório remoto e as mescla automaticamente com seu branch atual.

```bash
git pull origin main
```

- Isso busca e mescla as alterações do branch `main` no repositório `origin` com seu branch local.

- Cuidado: Se houverem conflitos, você precisará resolvê-los manualmente.

---

### Push

O `git push` envia suas alterações locais para o repositório remoto. Você só pode fazer push de commits que ainda não estão no repositório remoto.

```bash
git push origin main
```

- Isso envia seus commits locais no branch `main` para o repositório remoto `origin`.