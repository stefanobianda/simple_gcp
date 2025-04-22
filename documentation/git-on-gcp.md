# GIT

## Installa Git

Se non lo hai già fatto, esegui nella tua VM:

```
sudo apt update
sudo apt install git -y
```

Verifica:

```
git --version
```

## Genera una chiave SSH per GitHub

```
ssh-keygen -t ed25519 -C "stefanobianda@ik.me"
```

Premi ENTER a tutte le domande per usare il path di default (/home/tuo_utente/.ssh/id_ed25519).

Poi:

```
cat ~/.ssh/id_ed25519.pub
```

Copia il contenuto della chiave pubblica.

## Aggiungi la chiave su GitHub

Vai su https://github.com/settings/keys

Clicca New SSH Key

Dai un nome (es: GCP e2-micro)

Incolla la chiave pubblica nel campo

Salva

## Testa la connessione SSH a GitHub

```
ssh -T git@github.com
```

Dovresti vedere:

Hi tuo-username! You've successfully authenticated...

## Clona il tuo repo

Ora puoi clonare un repository privato o pubblico:

```
git clone git@github.com:stefanobianda/simple_gcp.git
```
Se è un repo pubblico, puoi anche usare HTTPS:

```
git clone https://github.com/stefanobianda/simple_gcp.git
```

