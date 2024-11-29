# PostgreSQL lokāla servera setup uz Linux

## Nepiecieciešamais
- Linux distribūcija (ieteicams Ubuntu)
- Sudo piekļuve
- Interneta savienojums

## Instalācijas soļi

### 1. Atjaunot pakotņu sarakstus
```bash
sudo apt update
sudo apt upgrade
```
### 2. Instalēt PostgreSQL
```
sudo apt install postgresql postgresql-contrib
```
### 3.  Pārbaudam lejupielādi
```
psql --version
sudo systemctl status postgresql
```
### 5. Pamata konfigurācija
- lietotāja izveide, ja nepieciešams
```
sudo -u postgres createuser --interactive
```
- jaunas datubāzes izveides veids:
```
sudo -u postgres createdb testdb
```
- paroles uzstādīšana lietotājam
```
sudo -u postgres psql
\password postgres
```
### 6. Porta pārbaude
```
ss -nlt | grep 5432
```


