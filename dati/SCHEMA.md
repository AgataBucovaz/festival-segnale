# Scheda dati

## Entità: Evento

| Campo | Tipo | Esempio |
|---|---|---|
| `id` | numero intero | `1` |
| `titolo` | stringa | `"Lettere in movimento"` |
| `data` | stringa, formato `AAAA-MM-GG` | `"2026-06-12"` |
| `orario` | stringa, formato `HH:MM` | `"10:00"` |
| `categoria` | stringa | `"Incontro"` |
| `descrizione` | stringa | `"Come cambia un messaggio quando cambiano le lettere? Un incontro su tipografia, ritmo e comunicazione visiva."` |
| `immagine` | stringa | `"assets/lettere-in-movimento.svg"` |
| `immagine_alt` | stringa | `"Lettere geometriche disposte su una griglia"` |
| `sede_id` | numero intero | `1` |

**Chiave primaria:** `id`, numerica, univoca nell’entità e stabile.

## Entità: Sede

| Campo | Tipo | Esempio |
|---|---|---|
| `id` | numero intero | `1` |
| `nome` | stringa | `"Officina Nord — Sede centrale"` |
| `indirizzo` | stringa | `"Corso Duca degli Abruzzi 24, Torino"` |

**Chiave primaria:** `id`, numerica, univoca nell’entità e stabile.

## Relazione

Una sede può ospitare più eventi; ogni evento si svolge in una sede.  
`Evento.sede_id` fa riferimento a `Sede.id`.

## Quantità

Il dataset comprende sei eventi e tre sedi.

## Aggiornamento e pubblicazione

Chi cura il progetto aggiorna i dati modificando i file JSON nella repository e pubblicando le modifiche.

## Che cosa mostra la pagina

La pagina mostra gli appuntamenti del festival, con data, orario, categoria, titolo, descrizione, immagine e sede.

## Schema Evento–Sede

```mermaid
erDiagram
    SEDE ||--o{ EVENTO : ospita
    SEDE {
        int id PK
        string nome
        string indirizzo
    }
    EVENTO {
        int id PK
        string titolo
        string data
        string orario
        string categoria
        string descrizione
        string immagine
        string immagine\_alt
        int sede\_id FK
    }
