# PostgreSQL lokāla servera setup uz Linux

## Sistēmas Prasības
1. Linux distribūcija (ieteicams Ubuntu 20.04 vai jaunāka)
2. Atmiņa (RAM): 2GB
3. Disku vieta: 2GB 
4. Interneta savienojums
5. Procesors: 1GHz vai vairāk

## Instalācijas soļi

### 1. Atjaunot pakotņu sarakstus
```bash
sudo apt update # Atjaunina pieejamās pakotnes 
```
### 2. Instalēt PostgreSQL
```
sudo apt install postgresql postgresql-contrib # Nolādē pieejamo sistēmas versiju PostgreSQL
```
### 3.  Pārbaudam lejupielādi
```
psql --version # Pārbauda versiju
sudo systemctl status postgresql # Pārbauda PostgreSQL pakalpojuma statusu (darbojas vai nē)
```
- lai startētu manuāli servisu
```
sudo systemctl start postgresql
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

### 6. Testēšana
1. Savienojamies ar PostgreSQL

```
sudo -u postgres psql
```
2. Izveido datubāzi
```
CREATE DATABASE testdb;
```
3. Savienojamies ar datubāzi

```
\c testdb
```
4. Izveidojam tabulu
```
CREATE TABLE students (id SERIAL PRIMARY KEY, name VARCHAR(100), age INT);
```
5. Ievietojam datus
```
INSERT INTO students (name, age) VALUES ('Alice', 20), ('Bob', 22);
```
6. Izvadam datus
```
SELECT * FROM students;
```
7. Papildus komandas testēšanai:
```
\l #saraksts ar datubāzēm;

\q #izešana no postgre termināļa;

\du #saraksts ar visiem lietotājiem;

\dt #saraksts ar tabulām
```

