# procedure.sql

Uma empresa precisa criar um relatório que faça um levantamento diário da quantidade de produtos comprados no dia. Para isso, crie um procedure que será usado para agilizar todos os processos.

CREATE PROCEDURE daily_product_report()
BEGIN
  SELECT 
    DATE(purchase_date) AS purchase_date,
    product_name, 
    SUM(quantity) AS total_quantity 
  FROM 
    purchases 
  GROUP BY 
    DATE(purchase_date), 
    product_name;
END;

CALL daily_product_report();

