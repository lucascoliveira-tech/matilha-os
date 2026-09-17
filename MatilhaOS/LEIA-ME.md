# MatilhaOS — guia do protótipo

Referência: projeto MAT do Jira, consultado em 17/09/2026. O nome encontrado foi MatilhaOS; o pedido original o chamou de Martila IA.

## Como explorar

O protótipo abre na visão geral. No menu superior, abra “Perfil e sessão” para testar Gestor, Recepção, Monitor e Financeiro. Para ver o login, escolha Sair. Use **demo@matilha.local** e **matilha123**. A recuperação de senha é simulada.

A data de demonstração é **17/09/2026**. As alterações são armazenadas somente no navegador. Em “Sobre o protótipo”, é possível restaurar os dados fictícios.

## Roteiro de validação

1. Na visão geral, observe 4 cães presentes e os alertas de Nina e Luna.
2. Em Check-in, tente registrar Nina sem justificativa: a vacina vencida exige autorização do Gestor. Registre uma justificativa e confirme. A presença aumenta e um crédito é consumido.
3. Registre Chico: o plano de diária gera uma cobrança. A repetição da entrada é bloqueada.
4. Faça check-out: escolha uma pessoa autorizada, confira os pertences e registre o resumo do dia.
5. Crie uma reserva recorrente entre 21 e 25/09, selecionando segunda, quarta e sexta. Revise as três ocorrências antes de confirmar.
6. No Financeiro, abra uma fatura, registre um pagamento demonstrativo e baixe o recibo. Gerar a mesma mensalidade novamente não duplica a fatura.
7. Troque para Monitor: financeiro, agenda e operações da recepção deixam de aparecer. Troque de unidade: as presenças e cães são filtrados.
8. Consulte relatórios de ocupação, frequência e financeiro, altere os filtros e exporte CSV.

## Cobertura das histórias de uso

| Área | Histórias Jira | Onde explorar |
|---|---|---|
| Acesso | [MAT-15](https://lucascoliveiragti.atlassian.net/browse/MAT-15) a MAT-18 | Sessão → Sair / perfis e seletor de unidade |
| Creche e equipe | [MAT-19](https://lucascoliveiragti.atlassian.net/browse/MAT-19) a MAT-23 | Configurações |
| Tutores | [MAT-24](https://lucascoliveiragti.atlassian.net/browse/MAT-24) a MAT-27 | Tutores → Cadastro e pessoas autorizadas |
| Cães | [MAT-28](https://lucascoliveiragti.atlassian.net/browse/MAT-28) a MAT-35 | Cães → Cadastro em etapas e ficha |
| Planos | [MAT-36](https://lucascoliveiragti.atlassian.net/browse/MAT-36) a MAT-40 | Planos e contratos / ficha do cão |
| Reservas | [MAT-41](https://lucascoliveiragti.atlassian.net/browse/MAT-41) a MAT-45 | Agenda → Nova reserva |
| Entrada e saída | [MAT-46](https://lucascoliveiragti.atlassian.net/browse/MAT-46) a MAT-53 | Check-in / Check-out |
| Presença | [MAT-54](https://lucascoliveiragti.atlassian.net/browse/MAT-54) a MAT-58 | Cães presentes / Histórico / Frequência |
| Faturamento | [MAT-59](https://lucascoliveiragti.atlassian.net/browse/MAT-59) a MAT-66 | Financeiro / presença → serviço adicional |
| Visão geral | [MAT-67](https://lucascoliveiragti.atlassian.net/browse/MAT-67) a MAT-71 | Visão geral e alertas |
| Notificações | [MAT-72](https://lucascoliveiragti.atlassian.net/browse/MAT-72) a MAT-74 | Notificações / Financeiro → simular cobrança |
| Relatórios | [MAT-75](https://lucascoliveiragti.atlassian.net/browse/MAT-75) a MAT-78 | Relatórios → filtros e exportação |

## Limites da entrega

Esta entrega é um protótipo interativo de frontend, não uma implementação de produção. As 64 histórias funcionais orientam as telas e simulações. Requisitos de backend e infraestrutura não são declarados concluídos.

- Login e recuperação, permissões e separação de unidades são demonstrações locais; não há provedor de identidade, validação JWT, RLS ou isolamento real entre empresas.
- Convites e cobranças por e-mail são simulados, sem envio externo.
- Pagamentos são registros fictícios; não há gateway financeiro.
- Fotos e documentos pequenos podem ser carregados para armazenamento local. Não há buckets privados ou URLs assinadas.
- Relatórios e exportações usam dados locais; o processamento assíncrono de servidor e URLs temporárias não estão conectados.
- A implementação do protótipo usa HTML, CSS e JavaScript. Angular 22, Spring, PostgreSQL, Cloud Run, Firebase Hosting, Terraform, CI/CD, monitoramento e requisitos TEC do Jira permanecem para a implementação de produção.
- Não há funcionalidade de IA especificada nas 64 histórias consultadas; nenhuma integração de IA foi inventada.

## Verificação realizada

17 grupos de verificações de lógica: renderização dos módulos e abas, bloqueio de vacina vencida, exceção justificada, consumo de crédito, prevenção de duplicidade, saída autorizada, cobrança por diária, geração mensal sem duplicação, pagamento, recorrência, dia fechado, capacidade, filtragem por unidade, perfil Monitor e auditoria. Verificação visual e de interação no navegador complementou os testes.

## Origem da imagem

Retrato de cão por Shubham Patil, [WordPress Photo Directory](https://wordpress.org/photos/photo/18068c2884/), CC0. Uso como foto fictícia do cão Bento.

