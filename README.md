# MatilhaOS

Protótipo interativo para gestão de creches caninas e banho e tosa, com dados fictícios.

[**Abrir demonstração pública**](https://matilhaos-prototipo-serena.lucascoliveira-gti.chatgpt.site) · [**Abrir banho e tosa**](https://matilhaos-prototipo-serena.lucascoliveira-gti.chatgpt.site/#grooming)

## Executar localmente

Requisito: Python 3 para servir os arquivos. Não há instalação de dependências nem etapa de build.

Na raiz do repositório:

```sh
python3 -m http.server 4173 --directory MatilhaOS
```

Acesse http://localhost:4173. No Windows, se necessário, use `py -m http.server 4173 --directory MatilhaOS`.

A aplicação abre na visão geral. Em **Perfil e sessão**, alterne entre Gestor, Recepção, Monitor e Financeiro. Para testar a tela de login, saia e use `demo@matilha.local` / `matilha123`. Essas credenciais pertencem exclusivamente à simulação.

A data de referência é **17/09/2026**. Alterações ficam no armazenamento local do navegador; podem ser restauradas em **Sobre o protótipo**. Fontes externas requerem internet; há fontes alternativas do sistema.

## Funcionalidades

- Dashboard, tutores, cães, saúde, vacinas e documentos.
- Agenda, reservas recorrentes, capacidade, check-in, check-out e frequência.
- Planos, créditos, faturamento, pagamentos demonstrativos, recibos e CSV.
- Banho e tosa: serviços e preços por porte, profissionais, conflitos de agenda, recebimento, execução, conclusão, retirada autorizada e cobrança única.
- Configurações, perfis demonstrativos, unidades e auditoria local.

## Estrutura

- `MatilhaOS/index.html`: entrada do protótipo.
- `MatilhaOS/app.js`: operação da creche e estado local.
- `MatilhaOS/grooming.js`: módulo de banho e tosa.
- `MatilhaOS/style.css`: estilos responsivos.
- `MatilhaOS/bento.jpg`: imagem demonstrativa existente.
- `MatilhaOS/LEIA-ME.md`: roteiro de validação, cobertura do Jira e limites.
- `tests/`: verificações de lógica executadas em ambiente Node com DOM simulado.

## Testes

Requisito: Node.js 20 ou superior. Não há bibliotecas externas.

```sh
node tests/prototype.test.cjs
node tests/grooming.test.cjs
```

São 34 grupos de verificações, incluindo duplicidade de check-in/cobranças, créditos, retirada autorizada, reservas, perfis, conflitos de agenda e o fluxo de banho e tosa. Estes testes de lógica não substituem testes ponta a ponta em navegador ou validação de segurança de produção.

## Escopo

As 64 histórias funcionais do projeto MAT orientaram o protótipo original. Banho e tosa foi acrescentado posteriormente como ampliação aprovada; não foram encontrados requisitos específicos desse módulo no Jira consultado.

Autenticação, permissões, pagamentos, e-mails e infraestrutura de produção são simulados. O protótipo usa HTML, CSS e JavaScript; não representa uma entrega de backend Spring, Angular, PostgreSQL ou infraestrutura GCP. Não use dados reais ou sensíveis nesta demonstração.

[Guia completo e cobertura dos requisitos](MatilhaOS/LEIA-ME.md).

## Imagem

Foto por Shubham Patil, [WordPress Photo Directory](https://wordpress.org/photos/photo/18068c2884/), CC0.
