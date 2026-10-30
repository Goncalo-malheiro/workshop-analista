[Uploading README.md…]()
# Analista por uma Noite · página do bilhete

Página de inscrição do workshop exclusivo de 11 de novembro, às 21h00.
Segue o padrão das outras campanhas: quatro ficheiros na raiz, deploy no Vercel, formulário enviado diretamente para o Kit.

| Ficheiro | O que é |
| --- | --- |
| `index.html` | A página do bilhete, com o formulário |
| `sucesso.html` | A página que aparece depois da inscrição (`/sucesso`) |
| `vercel.json` | URLs limpos (`/sucesso` em vez de `/sucesso.html`) |
| `README.md` | Este guia |

## 1. No Kit (10 minutos)

Os nomes dos menus podem variar ligeiramente.

1. **Cria um formulário novo**, do tipo inline, com o nome `Workshop nov26`. O desenho do formulário no Kit não interessa: a página usa o seu próprio.
2. **Email de incentivo:** liga o envio, cola o texto da secção "Email do bilhete" abaixo e anexa o Playbook em PDF como download.
3. **Depois de confirmar:** redireciona para o link do chat público do Investor Circle na Whop.
4. **Depois de subscrever:** escolhe "redirecionar para uma página" e mete `https://O-TEU-DOMINIO/sucesso` (fazes isto depois do deploy, no passo 3).
5. **Campo personalizado:** cria um campo chamado `origem`. É ele que te diz se a pessoa veio da Whop ou da newsletter.
6. **Copia o número do formulário.** Aparece no URL do editor e no código de embed (`app.kit.com/forms/NUMERO/...`).

Não precisas de tag: para os lembretes e para medir, filtras os subscritores por este formulário.

## 2. Nos ficheiros

1. Em `index.html`, troca `FORM_ID` pelo número do formulário.
2. Em `sucesso.html`, troca `WHOP_CHAT_URL` pelo link do chat público da Whop.
3. Se mudares o nome do workshop, procura e substitui `Analista por uma Noite` nos dois ficheiros. No `index.html` o título grande está partido em duas linhas (`Analista<br><em>por uma Noite</em>`), e no `sucesso.html` o nome também está no link do Google Calendar (`Analista%20por%20uma%20Noite`).

## 3. Deploy

1. Cria um repositório novo no GitHub (por exemplo `workshop-analista`) e mete os quatro ficheiros na raiz.
2. No Vercel: Add New Project, importa o repositório e faz Deploy. Não há build: é HTML estático.
3. Copia o domínio que o Vercel te der e volta ao passo 1.4 para meter o redirecionamento para `/sucesso`.

## 4. Links a usar

| Onde | Link |
| --- | --- |
| Mensagem fixada no chat da Whop | `https://O-TEU-DOMINIO/?origem=whop` |
| Email para a newsletter | `https://O-TEU-DOMINIO/?origem=newsletter` |

## 5. Teste antes de publicar

- [ ] Inscreve-te com o teu email: a página vai para `/sucesso`
- [ ] O email do bilhete chega, com o Playbook
- [ ] No Kit, apareces no formulário com o campo `origem` preenchido
- [ ] Repete no telemóvel
- [ ] Abre o link do chat da Whop a partir da página de sucesso

## Email do bilhete

**Assunto:** O teu bilhete para o Analista por uma Noite

> Olá {{ subscriber.first_name }},
>
> Está feito: tens lugar no workshop.
>
> **Quarta-feira, 11 de novembro, às 21h00**
> Ao vivo no chat do Investor Circle na Whop.
>
> Clica no botão abaixo para confirmares o teu email. É isso que te garante o Playbook agora e o link de acesso no dia.
>
> [botão de confirmação do Kit]
>
> Não precisas de ler o Playbook antes. Chegas e aprendes.
>
> Até dia 11,
> Gonçalo

O link de acesso ao workshop vai nos lembretes da véspera e de uma hora antes, enviados aos subscritores deste formulário.
