# Handye Eco Finance Tool

Aplicativo web de finanças pessoais que roda no computador e no celular (Android e iOS), sem instalar nada e sem cadastro. Ele calcula o **salário líquido**, mostra **quanto você gasta por mês**, quanto **sobra para guardar** e quanto você precisa poupar para **atingir uma meta em um prazo**.

Feito com HTML5, CSS3 e JavaScript puro (sem frameworks nem dependências). É um PWA: pode ser instalado na tela inicial e funciona offline.

**App online:** https://handyedev.github.io/handye-eco-finance-tool/

## Funcionalidades

- **Salário líquido:** do bruto, desconta INSS e Imposto de Renda (com dependentes), outros descontos e soma ganhos extras. Mostra 13º e férias aproximados.
- **Gastos mensais:** categorias editáveis, total e gráfico de pizza com a porcentagem de cada uma.
- **Meta com prazo:** informa quanto guardar por mês, quanto você terá se guardar toda a sobra, e em quanto tempo chega lá. Usa juros compostos e mostra um gráfico da evolução.
- **Regra 50/30/20:** compara seus gastos e sua poupança com essa referência.
- **Privacidade:** os dados ficam salvos só no seu aparelho (`localStorage`). Nada é enviado a servidor.
- **Bolinhas de ajuda (i):** passe o mouse ou toque na bolinha ao lado de termos como INSS, IRRF, dependentes, 13º, juros compostos e regra 50/30/20 para ver o que significam. Toque de novo, clique fora ou aperte Esc para fechar.
- Tema claro e escuro, layout responsivo e acessível (foco visível, rótulos nos campos).

## Como usar o aplicativo

1. **Seu salário:** no menu **"O valor que você vai informar é"**, escolha **Salário fixo bruto** (o app calcula INSS e IR) ou **Valor líquido** (o valor que cai na conta; nesse caso INSS e IR não são calculados). Depois digite o valor. No modo bruto, informe também dependentes (para o IR). Em ambos, se tiver, informe outros descontos (plano de saúde, vale-transporte) e ganhos extras (VR, renda extra). O app mostra o salário líquido na hora.
2. **Seus gastos:** ajuste os valores de cada categoria ou clique em **+ Adicionar gasto**. Use o ✕ para remover. A barra do topo mostra **Líquido, Gastos e Sobra** o tempo todo.
3. **Seu objetivo:** informe quanto quer acumular, em quantos meses, quanto já tem guardado e o rendimento esperado ao ano (use 0 para ignorar juros). O app diz quanto guardar por mês e se isso cabe na sua sobra. Se não couber, mostra quanto falta.
4. **Regra 50/30/20:** veja se seus gastos estão abaixo de 80% da renda e se a sobra chega a 20%.
5. **Limpar tudo** apaga seus dados e volta tudo para zero.

### Exemplo

Salário bruto de R$ 3.500, gastos de R$ 2.350 e meta de R$ 20.000 em 24 meses com 10% ao ano: líquido de R$ 3.191,40, sobra de R$ 841,40 e necessidade de guardar R$ 759,44/mês. A meta cabe na sobra.

## Como rodar

**No computador:** abra o `index.html` no navegador (dois cliques).

**Servindo localmente** (necessário para testar a instalação como PWA):

```bash
python -m http.server 8000
```

Depois acesse `http://localhost:8000`.

**No celular:** publique a pasta em um endereço `https` (GitHub Pages, Netlify ou Vercel), abra o link no celular e use **Adicionar à tela inicial**.

## Publicar no GitHub Pages

No repositório, vá em **Settings → Pages**, escolha a branch `main` e a pasta `/ (root)`. O site fica em `https://HandyeDEV.github.io/handye-eco-finance-tool/`.

## Estrutura

| Arquivo | Função |
|---|---|
| `index.html` | Telas, estilos e lógica do app |
| `manifest.json` | Configuração do PWA (nome, ícone, cores) |
| `sw.js` | Service worker (cache para uso offline) |
| `icon.svg` | Ícone do app |

## Atualizando as tabelas de impostos

As faixas de INSS e IRRF ficam no bloco `CFG`, no início do `<script>` do `index.html`. Atualize-as quando a legislação mudar (normalmente todo ano). Os valores atuais são os de 2026 que o autor conhecia; confira com a Receita Federal e a Previdência.

## Limites conhecidos

- O cálculo de INSS e IR é uma **estimativa**: não considera pensão alimentícia, previdência privada nem outras deduções.
- Os rendimentos usam uma taxa fixa informada por você; não consultam o mercado.
- Não substitui orientação de um profissional. Não é consultoria financeira.
- Testado no navegador do computador; a instalação no celular ainda não foi testada.

## Autor

Feito por **HandyeDEV**.
