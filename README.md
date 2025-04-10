# 🧠 Teste de Estágio 

## WebSockets

### Parte 1 – Conceito

Pesquise e explique com suas palavras:

- O que são WebSockets?
- Como funcionam?
- Quando é melhor usar WebSockets em vez de uma API REST tradicional?

### Parte 2 – Prática

Você deve criar um pequeno script que se conecta ao **servidor WebSocket** que criamos e descobrir **qual mensagem ele está enviando**.

#### ✅ O que você deve fazer:
1. Criar um pequeno código na linguagem que preferir
2. Estabelecer a conexão com o servidor WebSocket
3. Ler a mensagem recebida
4. Faça um **clone deste repositório**
5. Insira:
   - A **mensagem que você recebeu** aqui no `README.md`
   - O **código que você criou** no repositório
  
URL do servidor: websocket-fh6l.onrender.com

### Parte 3 - 🔎 Desafio teórico: Comunicação em tempo real entre usuários
Você precisa projetar um sistema simples de mensagens em tempo real para usuários logados.

---

#### 🧩 Cenário

O sistema permite que usuários escolham um **nome de usuário** ao entrar.

As mensagens podem ser:

- **Públicas**: todos os usuários conectados recebem.
- **Privadas**: enviadas para um **usuário específico** (por exemplo: `/msg joao oi`).

Outros requisitos:

- Um mesmo usuário pode estar conectado em **vários dispositivos ou abas ao mesmo tempo**.
- Se um usuário **cair e voltar**, ele deve continuar recebendo as mensagens normalmente.

---

#### ❓ Sua tarefa (teórica)

1. Que tipo de tecnologia de comunicação você usaria para esse cenário?

2. Como garantiria o envio correto para:
   - Todos os usuários?
   - Apenas um usuário específico?
   - Todas as sessões abertas de um mesmo usuário?

3. Existe alguma ferramenta ou biblioteca que facilitaria esse tipo de comunicação?  
   Se sim, **qual?** E **por quê?**

---

#### 🎯 Objetivo

Entender se você consegue identificar os desafios da comunicação em tempo real e pensar em soluções viáveis e escaláveis para eles.


## Boa sorte! 💻
