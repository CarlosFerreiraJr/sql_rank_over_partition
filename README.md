##  Função RANK OVER PARTITION - SQL Oracle 8i
Exemplo de utilização da Função RANK OVER PARTITION do SQL Oracle.<br>
A rotina SQL abaixo lista as 5 faturas mais recentes de todos os clientes de uma tabela.

### Rotina SQL
```
select  num_conta, num_fatura, dt_vencimento from (
SELECT 
        num_conta, num_fatura, dt_vencimento,
        rank () over (PARTITION BY num_conta ORDER BY dt_vencimento DESC) pos
from tab_faturas )
where pos <= 5		
```
