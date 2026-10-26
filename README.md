# You're in a cave — TryHackMe

Writeup for the TryHackMe room **[You're in a cave](https://tryhackme.com/room/youreinacave)**.

Writeup da room **[You're in a cave](https://tryhackme.com/room/youreinacave)** do TryHackMe.

| | |
|---|---|
| **Platform / Plataforma** | TryHackMe |
| **Difficulty / Dificuldade** | Hard |
| **Tags** | `docker` · `privesc` · `rpg` · `regex` |
| **Theme / Tema** | Text-based RPG — each step is a "stage" of the adventure / RPG baseado em texto — cada etapa é uma "fase" da aventura |

---

## Read it / Leia

| Language / Idioma | File / Arquivo |
|-------------------|----------------|
| 🇧🇷 Português | **[`writeup/writeup-pt-br.md`](writeup/writeup-pt-br.md)** |
| 🇬🇧 English | **[`writeup/writeup-en.md`](writeup/writeup-en.md)** |

Screenshots: [`images/`](images/)

---

## About / Sobre

**EN** — A text-RPG style room: a TCP service on port 3333 takes "actions" as if it were a game, and that is where exploitation begins. The chain goes from arbitrary file read all the way to root on the machine's host. The writeup explains the *reasoning* behind each step — why `nc`, how the XXE was found and tested, and every pitfall that can silently waste hours.

**PT** — Room no estilo RPG de texto: um serviço TCP na porta 3333 recebe "ações" como se fosse um jogo, e é por ele que a exploração começa. A cadeia vai de leitura de arquivos até root no host da máquina. O writeup explica o *raciocínio* por trás de cada passo — por que `nc`, como o XXE foi achado e testado, e cada beco que pode custar horas em silêncio.

**Exploitation chain / Cadeia de exploração:**

```
XXE  →  Java deserialization (RCE)  →  SSH brute-force  →  GPG
     →  sudo abuse  →  root in container  →  cgroup release_agent escape  →  root on host
```

---

## Note on flags / Nota sobre as flags

**EN** — Flags, passwords and the passphrase are **redacted** (`████`), following TryHackMe's Acceptable Use Policy: publishing answers/solutions for active content is not allowed; 

**PT** — Flags, senhas e a passphrase estão **ofuscadas** (`████`), seguindo a Acceptable Use Policy do TryHackMe: publicar respostas/soluções de conteúdo ativo não é permitido; 
## Author / Autor

Daniel — [TryHackMe](https://tryhackme.com/p/Daniel8bit) · [GitHub](https://github.com/Daniel16Bit)
