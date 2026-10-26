# You're in a cave — TryHackMe

EN - Writeup for the TryHackMe room **[You're in a cave](https://tryhackme.com/room/youreinacave)**.

PT - Writeup da room **[You're in a cave](https://tryhackme.com/room/youreinacave)** do TryHackMe.

| | |
|---|---|
| **Platform / Plataforma** | TryHackMe |
| **Difficulty / Dificuldade** | Hard |
| **Tags** | `docker` · `privesc` · `rpg` · `regex` |
| **Theme / Tema** | Text-based RPG — each step is a "stage" of the adventure / RPG baseado em texto — cada etapa é uma "fase" da aventura |

---

## About / Sobre

**EN** — A text-RPG style room: a TCP service on port 3333 takes "actions" as if it were a game, and that is where exploitation begins. The chain goes from arbitrary file read all the way to root on the machine's host.

**PT** — Room no estilo RPG de texto: um serviço TCP na porta 3333 recebe "ações" como se fosse um jogo, e é por ele que a exploração começa. A cadeia vai de leitura de arquivos até root no host da máquina.

**Exploitation chain / Cadeia de exploração:**

```
XXE  →  Java deserialization (RCE)  →  SSH brute-force  →  GPG
     →  sudo abuse  →  root in container  →  cgroup release_agent escape  →  root on host
```

---

## Contents / Conteúdo

- **[`writeup/writeup-cave.md`](writeup/writeup-cave.md)** — full step-by-step writeup with the reasoning behind each stage / writeup completo, passo a passo, com o porquê de cada etapa
- **[`images/`](images/)** — screenshots

---

## Note on flags / Nota sobre as flags

**EN** — Flags, passwords and the passphrase are **redacted** in this writeup, following TryHackMe's Acceptable Use Policy (publishing answers/solutions for active content is not allowed; writeups are for retired content only). 

**PT** — Flags, senhas e a passphrase estão **ofuscadas** neste writeup, seguindo a Acceptable Use Policy do TryHackMe (publicar respostas/soluções de conteúdo ativo não é permitido; writeups são apenas para conteúdo aposentado). 

---

## Author / Autor

Daniel — [TryHackMe](https://tryhackme.com/p/Daniel8bit) · [GitHub](https://github.com/Daniel16Bit)
