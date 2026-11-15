# CNABSync

Ferramenta web para leitura, conciliação e auditoria posicional de arquivos bancários CNAB 240 e CNAB 400 (`.REM`, `.RET`, `.CRM`, `.CRT`), executada inteiramente no navegador.

Aplicação no ar: https://diogold01.github.io/cnabsync/

## O Problema

No suporte técnico a sistemas ERP, é comum investigar divergências de boletos rejeitados, baixas não processadas, diferenças de nosso número ou erros de estrutura em arquivos de remessa e retorno bancário. Fazer essa conferência abrindo arquivos posicionais de 240 ou 400 colunas em editores de texto comuns é lento e sujeito a erro humano.

O CNABSync foi construído em arquivo único HTML/JavaScript (com apoio de IA a partir das regras de negócio e manuais FEBRABAN) para permitir que o analista arraste os arquivos de remessa e retorno, visualize os campos decodificados por posição e compare divergências na hora.

## Funcionalidades

- **Conciliação Remessa x Retorno:** cruzamento automático entre títulos enviados na remessa e ocorrências devolvidas no retorno (liquidações, entradas confirmadas, rejeições e baixas), apontando divergências de valor, vencimento e nosso número.
- **Inspetor Posicional FEBRABAN:** visualização linha a linha do arquivo bruto com destaque de colunas (início, fim, tamanho e valor extraído) para cabeçalho, segmentos (`P`, `Q`, `R`, `T`, `U` no CNAB 240 e registros tipo `1` no CNAB 400) e rodapé.
- **Validação de Linha Digitável e Nosso Número:** conferência de dígitos verificadores (Módulo 10 e Módulo 11) e decomposição do campo livre quando uma linha digitável de boleto é informada para confronto.
- **Execução 100% local no navegador:** os arquivos selecionados são lidos via `FileReader` na memória do navegador; nenhum arquivo bancário ou dado de cliente é enviado para servidores externos.

## Limites Atuais

- A ferramenta roda exclusivamente no navegador por regras posicionais determinísticas (não possui backend nem chamadas a modelos de IA).
- As regras específicas de cabeçalho e decomposição de carteira/nosso número estão validadas principalmente para **Sicredi (748 - CNAB 400)**, **Caixa Econômica Federal (104 - CNAB 240)** e **Cresol (133 - CNAB 240)**, além de extração de campo livre para **Santander (033)**. Para os demais bancos listados na interface (Sicoob, Banco do Brasil, Bradesco e Itaú), o sistema aplica leitura posicional genérica do padrão FEBRABAN 240/400.

## Como Executar

Acesse diretamente pelo GitHub Pages em `https://diogold01.github.io/cnabsync/` ou abra o arquivo `index.html` em qualquer navegador moderno.
