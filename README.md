# 🧠 Teste de Estágio 

## Instruções
- Realize o git clone deste repositório
- Responda as perguntas no próprio Readme.md
- Suba o código no repositório
- Insira a mensagem retornada do servidor
- Nos envie o link do seu repositório

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

# Respostas:

## **Parte 1 - Conceito**

**1- O que são WebSockets?**

    Websocktes é um protocolo de comunicacao bidirecional, isso permite a troca continua de dados entre cliente 
    e servidor em tempo real,sua conexão é persistente, permiteindo a 
    troca de mensagens sem que o cliente fique fazendo requisicoes de constantemente em busca de atualizacoes.

**2-Como funcionam?**

    Um websocket comeca fazendo um requisicao HTTP para o servidor para estabelecer a 
    conexão,uma vez aceita a comunicação é mantida de forma persistente,
    e as mensagens podem fluir em ambas as direções.
    Quando a conexão é realizada , tanto o cliente quanto o 
    servidor prodem enviar mensagens a qualquer momento 
    sem a necessidade de uma solicitação explicita.

**3-Quando é melhor usar WebSockets em vez de uma API REST tradicional?**

	  É melhor usar Websocket em situacoes que se exige uma 
     comunicação em tempo real, onde existe uma alta taxa 
     de atualização de dados e interações bidirecionais.

## Parte 2 - Prática

**Script:**

import websocket

def on_message(ws, message):
    print(f"Mensagem recebida: {message}")

def on_error(ws, error):
    print(f"Erro: {error}")

def on_close(ws, close_status_code, close_msg):
    print("Conexão fechada")

def on_open(ws):
    print("Conexão estabelecida com sucesso")

if __name__ == "__main__":
    url = "wss://websocket-fh6l.onrender.com"
    websocket.enableTrace(True)
    ws = websocket.WebSocketApp(url,on_message=on_message,on_error=on_error,on_close=on_close,on_open=on_open)
    ws.run_forever()

**Mensagem Recebida: "Olá mundo! LTIS 2025"**


## Parte 3 - Desafio Teórico:

	1- Como o cenário se trata de troca de mensagem simultaneamente, o ideia seria utilizar 
     Websockets com suporte a canais/salas,pois as trocas de mensagens pode ser feitas de 
     maneira pública ou de maneira privada(usuários específicos).
	
	2-Para garantir o envio correto para todos os usuario é utilizar 
     um canal no websocket em que todos os usuários estão inscritos,
     criar um grupo geral.Para enviar a mensagem para um usuário 
     específico a criação de uma tabela/mapa que associe os nomes de 
     usuários às conexões websockets(os usuários irão escolher o nome 
     que entrarão),ssim quando se envia a mensagem, ira ocorrer a verificação 
     de qual é o destinatario e para onde ela deve ser entregue.E para todas as 
     sessões de um mesmo usuário é necessário gerar múltiplas conexões para o mesmo
     ,criando uma estrutura de dados que associe cada um a uma lista de conexões ativas.
     Quando uma mensagem é enviada e o destinatário esta conectado em diversas abas o próprio
     ,o servidor iterará sobre todas as conexões e enviará a mensagem para todas conexões.

	3-Existe a biblioteca Sockt.io e as ferramentes Pusher e Firebase.A biblioteca Sockte.io 
     fornece comunicação em tempo real com suporte a reconexões automáticas e criação e gerenciamento de salas, 
     tanto públicas quanto privadas.Já a Pusher é mais focado em mensagens em tempo real, 
     notificações e facilita o gerenciamento de canais e eventos em tempo real, ideal para mensagens instantâneas. 
     E a Firebase é uma plataforma mais abrangente, oferecendo uma variedade de serviços, 
     incluindo banco de dados em tempo real, autenticação, armazenamento de dados e muito mais
