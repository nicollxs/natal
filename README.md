# Encanto — loja de Natal
Landing page mobile-first com checkout demonstrativo, construída com Next.js App Router, React, TypeScript e Tailwind CSS.

## Executar localmente
Node.js 22.15 ou superior.
```sh
npm ci
npm run dev
```
Abra http://127.0.0.1:3000.
```sh
npm run typecheck
npm test
npm run build
npm start
```

## Oferta
Preço do conjunto: **R$ 89,90**, frete à parte. Conteúdo editável em `lib/product.ts`.
Composição aproximada: 8 bolas douradas médias, 8 vermelhas médias, 6 douradas grandes, 6 vermelhas grandes e 9 adornos decorativos, além de pisca-pisca simples e laço grande no topo. Quantidades e características finais dependem de conferência no recebimento.

A imagem ativa `public/arvore-ilustrativa-v5.webp` foi criada com IA e é identificada como ilustração. Não é foto do produto recebido. Arquivos originais e versões antigas foram preservados localmente, fora do repositório. Prompts de criação incluídos nos arquivos `PROMPT-IMAGEM*.txt`.

## Funcionalidades
- Layout responsivo e ajustes específicos para celular.
- Efeitos natalinos com pausa e respeito a movimento reduzido.
- Quantidade preservada apenas na sessão do navegador.
- Consulta demonstrativa de CEP e frete.
- Checkout sem conta, campos validados, revisão e resumo recolhível.
- Resultados simulados de pagamento aprovado, pendente e recusado.
- Seção de transparência, composição, FAQ e políticas provisórias.

## Limites da demonstração
**Não recebe pagamentos, reservas ou pedidos reais.**
Frete de R$ 35,00 e prazo de 5 a 8 dias úteis são exemplos. CEPs com prefixo de quatro dígitos entre 0100 e 5999 são aceitos para teste: 01001-000 aceito; 90000-000 bloqueado.
Os dados do formulário ficam apenas em memória. Não há banco de pedidos, e-mail transacional, atendimento conectado ou painel administrativo.
Bravo Pay, Meta Pixel e Conversions API ainda não estão integrados. Não existe variável que ative cobrança.

## Arquitetura
- `app/`: landing page, checkout e políticas.
- `components/`: oferta, marca, quantidade, efeitos e transparência.
- `lib/product.ts`: preço, composição, condições de teste e pendências.
- `lib/commerce.ts`: validação de quantidade, frete e cálculos em centavos.
- `lib/payment.ts`: contrato demonstrativo e modelo de pedido.
- `lib/analytics.ts`: estrutura de UTMs, sem rastreamento ativo.
- `tests/`: regras de valores, cobertura e estados de pagamento.

## Publicar na Vercel
Importe este repositório, selecione o preset Next.js e mantenha a raiz do projeto em `./`. Use Node.js 22.x, instalação `npm ci` e build `npm run build`. A Vercel determina a saída automaticamente. Esta versão não exige credenciais.
Publicar o projeto disponibiliza uma **demonstração**, sem ativar vendas.

## Antes da operação real
Confirmar identificação e contato da loja, estoque, medidas, material, montagem, composição, especificações elétricas, cobertura, frete, prazo e políticas.
Implementar o gateway com sua documentação oficial, cálculo autoritativo no servidor, persistência em banco, webhook autenticado, idempotência e e-mail transacional. Nunca aprovar pagamento pelo redirecionamento do navegador.
Configurar gestão protegida de pedidos, domínio, metadados de compartilhamento, privacidade e consentimento. Configurar mensuração sem duplicidade; Purchase somente após confirmação real.

## Validação
Build de produção, TypeScript e quatro testes automatizados aprovados. Fluxo de compra conferido no navegador, inclusive CEP fora de cobertura e estados de pagamento. Layout conferido em larguras de 320, 390 e 430 px e desktop.
Pendente: testes em aparelhos físicos e nos navegadores internos do Instagram/Facebook.
