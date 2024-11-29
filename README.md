# PostgreSQL lokāla servera setup uz Linux

## Nepiecieciešamais
- Linux distribūcija (ieteicams Ubuntu)
- Sudo piekļuve
- Interneta savienojums

## Instalācijas soļi

### 1. Atjaunot pakotņu sarakstus
```bash
sudo apt update # Atjaunina pieejamās pakotnes 
sudo apt upgrade # Atjaunina pakotnes uz jaunākajām pakotnēm
```
### 2. Instalēt PostgreSQL
```
sudo apt install postgresql postgresql-contrib
```
### 3.  Pārbaudam lejupielādi
```
psql --version # Pārbauda versiju
sudo systemctl status postgresql # Pārbauda PostgreSQL pakalpojuma statusu (darbojas vai nē)
```
### 5. Pamata konfigurācija
- lietotāja izveide, ja nepieciešams
```
sudo -u postgres createuser --interactive # seko promptiem
```
- jaunas datubāzes izveides veids:
```
sudo -u postgres createdb testdb
```
- paroles uzstādīšana lietotājam(postgres piemērs)
```
sudo -u postgres psql
\password postgres
```
### 6. Porta pārbaude
```
ss -nlt | grep 5432 # Lai pārbaudītu statusu, jābūt 200
```


