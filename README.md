# Convite Digital — Luciene Vilela

Convite digital criado para a celebração de **Luciene Vilela**, integrando identidade visual, confirmação de presença e conexão com Google Sheets por meio de Google Apps Script.

**Evento:** 26 de setembro de 2026, às 20h  
**Local:** Clube Espanhol — Av. Oceânica, 1404, Ondina, Salvador/BA  
**Prazo padrão de confirmação:** 20 de setembro de 2026

---

## Objetivo

O convite foi criado para:

- apresentar as informações do evento;
- manter a identidade visual da celebração;
- permitir confirmação de presença;
- registrar convidado principal e acompanhantes;
- enviar os dados diretamente para a planilha;
- bloquear confirmações após a data-limite;
- permitir alteração simples do prazo sem editar o HTML.

---

## Estrutura do projeto

Exemplo:

```text
/
├── index.html
├── styles.css
├── README.md
└── assets/
    ├── LV_DOURADO.png
    ├── cosmeedamsemfundo.png
    ├── trevo-estilo-sao-cosme-damiao.png
    └── demais imagens
```

O Google Apps Script não deve ser hospedado junto com a página.

---

## Identidade visual

O convite utiliza:

- fundo branco/champagne;
- dourado;
- logo LV;
- tipografia elegante;
- círculos decorativos animados;
- ilustração de São Cosme e São Damião;
- trevo como elemento gráfico;
- cartões de localização e traje;
- layout responsivo para desktop e celular.

---

## Informações do evento

O convite apresenta:

- Luciene Vilela;
- celebração de aniversário;
- tradicional Caruru de São Cosme e Damião;
- sábado, 26 de setembro de 2026;
- 20h;
- Clube Espanhol;
- Salvador/BA;
- sugestão de traje branco.

---

## Confirmação de presença

O formulário envia:

- nome do convidado;
- familiares/acompanhantes.

Os dados são enviados ao Google Apps Script, que grava na planilha.

A URL do Web App usada no projeto é:

```text
https://script.google.com/macros/s/AKfycbyJou8QsnvKEPTyq4AJmAIk_Bog7hGOnUxEMvdouUwk_oL-mF7u4kLIWV7Xh9zaLJO0aw/exec
```

---

## Prazo de confirmação

A data-limite fica centralizada no Google Apps Script.

Exemplo:

```javascript
const DATA_LIMITE_RSVP = "2026-09-20";
```

Isso significa que o convite aceita confirmações até:

```text
20/09/2026 às 23:59
```

A partir de 21/09/2026, o sistema bloqueia novas confirmações.

---

## Como alterar o prazo

Para estender o prazo até 25 de setembro, alterar apenas:

```javascript
const DATA_LIMITE_RSVP = "2026-09-25";
```

Depois:

1. salvar o Apps Script;
2. abrir `Implantar`;
3. abrir `Gerenciar implantações`;
4. editar a implantação atual;
5. escolher `Nova versão`;
6. implantar novamente.

O convite consulta essa configuração automaticamente.

---

## Estado de prazo encerrado

Quando o prazo acaba, o formulário deixa de aceitar novas respostas e passa a mostrar:

```text
Confirmações encerradas
```

A proteção acontece em dois níveis:

- interface do convite;
- backend do Google Apps Script.

Assim, mesmo uma tentativa direta de envio após a data-limite é recusada.

---

## Planilha

A confirmação é registrada na aba:

```text
Confirmações - Aniversário Luciene (Caruru)
```

Estrutura principal:

| Coluna | Conteúdo |
|---|---|
| A | Data/Hora |
| B | Nome |
| C | Familiares/Acompanhantes |
| D | Pessoas nesta confirmação |
| E | Total confirmado |

---

## Contagem de acompanhantes

O sistema reconhece vários acompanhantes separados por:

- vírgula;
- ponto e vírgula;
- `e`;
- `&`.

Exemplo:

```text
Ana, Bruno e Carlos
```

é interpretado como três acompanhantes.

---

## Publicação

O convite pode ser publicado no GitHub Pages.

No GitHub devem ficar apenas os arquivos do front-end.

Não publicar:

```text
apps-script.gs
```

O Apps Script permanece no Google.

---

## Atualização do Apps Script

Sempre que houver alteração no backend:

1. salvar o código;
2. abrir `Implantar`;
3. abrir `Gerenciar implantações`;
4. editar a implantação atual;
5. escolher `Nova versão`;
6. implantar.

Ao editar a mesma implantação, a URL `/exec` continua igual.

---

## Observação

O convite foi pensado para ser simples para o convidado e fácil de manter pelo responsável do evento.

A principal configuração operacional — a data-limite — fica centralizada no Apps Script.
