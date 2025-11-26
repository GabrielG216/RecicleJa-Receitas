# RecicleJá — Receitas

Visão geral
-----------
Pequeno projeto front-end que apresenta receitas de reaproveitamento (cascas, talos e sobras). Exibe cartões com foto e resumo, permite pesquisa em tempo real, abre modal com detalhes e possui footer fixo.

Funcionalidades
---------------
- Leitura de dados a partir de `lista.json`.
- Grid responsivo de cards para cada receita.
- Campo de pesquisa que filtra por nome, reaproveitamento e ingredientes.
- Modal com descrição, ingredientes, modo de preparo e tempo.
- Footer fixo no final da página.
- Estilos responsivos (media queries) para diferentes larguras.

Estrutura do projeto
--------------------
- `index.html` — página principal (HTML + JS embutido).
- `style.css` — estilos e media queries.
- `lista.json` — dados das receitas (array "receitas").
- `img/` — imagens referenciadas por `foto_url`.
- `README.md` — este arquivo.

Como executar localmente
------------------------
O fetch de `lista.json` requer servidor HTTP (não funciona via `file://`).

Opções rápidas:
- Python 3:
  - `python -m http.server 8000`
  - Abrir `http://localhost:8000`
- Node (http-server):
  - `npx http-server . -p 8000`
  - Abrir `http://localhost:8000`

Uso do sistema de pesquisa
--------------------------
- Campo de pesquisa acima dos cards (`input#searchInput`).
- A cada digitação o script filtra os cards comparando o texto com `data-tags` (contém nome, reaproveitamento e ingredientes em minúsculas).
- Busca por substring (case-insensitive). Exemplos: "banana", "casca", "farofa".

Editar / adicionar receitas
---------------------------
Edite `lista.json`. Cada receita deve seguir este modelo:

```json
{
  "id": 1,
  "nome": "Nome da receita",
  "reaproveitamento": "Parte reaproveitada",
  "foto_url": "img/exemplo.jpg",
  "descricao": "Descrição curta",
  "ingredientes": ["Ingrediente 1", "Ingrediente 2"],
  "modo_preparo": "Passos de preparo",
  "tempo_preparo": "Tempo"
}
```

Boas práticas
-------------
- Verifique a sintaxe JSON (vírgulas, aspas).
- Garanta que os caminhos em `foto_url` existam na pasta `img/`.
- Teste via servidor local antes de commitar.

Observações técnicas
--------------------
- O footer é fixo (`position: fixed`) e a `.container` tem `padding-bottom` para evitar sobreposição do conteúdo.
- O modal tem z-index maior que o footer (de modo que fique por cima).
- Acessibilidade básica: input de pesquisa possui `aria-label`; imagens dos cards usam `alt`.

Melhorias sugeridas
-------------------
- Paginação ou carregamento sob demanda (lazy load) das imagens.
- Filtros por categorias/tags e pesquisa com múltiplos termos.
- Salvar receitas favoritas em localStorage.
- Separar JS em arquivo externo para melhor manutenção.

Publicando no Git
-----------------
Comandos básicos:
```bash
git init
git add .
git commit -m "Primeiro commit — RecicleJá"
git remote add origin <url-do-repositorio>
git branch -M main
git push -u origin main
```

Licença / Créditos
------------------
Projeto educativo. Ajuste licença conforme necessidade. Créditos aos autores do HTML/CSS/JS presentes no repositório.
