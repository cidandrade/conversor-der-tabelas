# Conversor DER → Tabelas

Página interativa (mobile-first) que leva do **modelo conceitual** ao **modelo lógico**. O aluno ajusta as cardinalidades de um relacionamento e vê, ao vivo:

- a frase que a cardinalidade diz (“cada funcionário se liga a exatamente 1 departamento”);
- a linha da tabela de regras de implementação (tabela própria, adição de coluna ou fusão, com ✔ / ± / ✘);
- o modelo lógico na notação da apostila;
- o que o banco consegue garantir e o que fica para trigger ou aplicação;
- o script **MySQL** (`CREATE TABLE` com PK, FK, `UNIQUE` e `CHECK`), com as linhas que mudaram acesas.

Material da disciplina **Modelagem de Banco de Dados** — Prof. Cid Andrade (UNICID). As regras seguem a Apostila de MBD, p. 30–36 (a partir de Heuser, *Projeto de Banco de Dados*).

## As três abas

| Aba | Conteúdo |
|-----|----------|
| Relacionamento binário | 9 cenários, entre eles 2 autorrelacionamentos (Empregado gerencia, Animal predação); as 16 combinações de cardinalidade; as 3 alternativas de implementação |
| Outros casos | ternário (chaves candidatas a partir dos máximos), entidade associativa (Consulta/Prescrição), generalização total ou parcial (uma tabela ou uma por entidade), atributo multivalorado, identificador externo |
| Treino de cardinalidade | 10 frases de regra de negócio; o aluno escreve a cardinalidade de cada lado, e a página avisa quando ele troca os lados |

O endereço guarda o estado do conversor: `index.html#c=lotacao&a=11&b=0n&alt=1` abre direto em Departamento × Funcionário, (1,1)–(0,n), adição de coluna. Serve para pôr um caso específico num slide.

## Arquivos

- `index.html` — a página (arquivo único; só usa Google Fonts de fora).

## Verificação

Todos os 560 scripts que a página gera (cada cenário × cardinalidade × alternativa × com ou sem atributo, mais os casos especiais) rodaram sem erro no MySQL 8.4. As restrições que a página diz garantir foram testadas com `INSERT`s que devem ser recusados.

Requer **MySQL 8.0.16+**, para que os `CHECK` sejam respeitados.
