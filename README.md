# CnabSync

Ferramenta web em arquivo único para conferir arquivos de remessa e retorno bancário (CNAB 240 e CNAB 400) direto no navegador.

## Para que serve

No dia a dia de quem emite boletos, conferir manualmente o que foi enviado na remessa, o que o banco confirmou, o que foi pago e o que ficou sem retorno ou rejeitado exige abrir vários arquivos de texto.

O CnabSync lê as pastas de remessa e retorno localmente, cruza os títulos pelo nosso número e mostra em uma tela só:
- quais boletos foram pagos, confirmados ou rejeitados (com o motivo do banco);
- quais remessas estão sem retorno;
- saltos na numeração sequencial (NSA) dos arquivos de retorno;
- busca rápida por pagador, CPF/CNPJ, nosso número ou linha digitável (44/47 dígitos);
- exportação do resultado e das divergências em CSV e JSON.

## Privacidade

Tudo roda no seu navegador. Nenhum arquivo CNAB sai do computador ou é enviado para servidor.

## Bancos suportados

Sicredi (748), Cresol (133), Caixa Econômica (104), Santander (033), Safra (422), Sicoob (756), Banco do Brasil (001), Bradesco (237) e Itaú (341).
