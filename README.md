# Corona-virus-ometer
Python 3.8.0
Required packages:
```
pip3 install mysql-connector-python
pip3 install beautifulsoup4
```
Uses webscraping to collect information of the corona virus off the web and stores it in a database.

**connection.php and index.php are help on the webserver.
Everything else is stays in the same folder and is executed by running main.py**

**Trigger for tbl_Outbreak**

Time: Before

Event: Insert
```sql
INSERT INTO tbl_OutbreakHistory (Country, Infected, Dead, Continent, Date) VALUES (new.Country, new.Infected, new.Dead, new.Continent, new.Date)
```
**Table Layout**
```sql
CREATE TABLE `tbl_Outbreak` (
 `Country` varchar(20) NOT NULL,
 `Infected` int(12) NOT NULL,
 `Dead` int(12) NOT NULL,
 `Continent` varchar(20) NOT NULL,
 `Date` datetime NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4

CREATE TABLE `tbl_OutbreakHistory` (
 `Country` varchar(20) NOT NULL,
 `Infected` int(12) NOT NULL,
 `Dead` int(12) NOT NULL,
 `Continent` varchar(20) NOT NULL,
 `Date` datetime NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4

CREATE TABLE `tbl_OutbreakTotals` (
 `Infected` int(11) NOT NULL,
 `Dead` int(11) NOT NULL,
 `Cured` int(11) DEFAULT NULL,
 `Date` datetime DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4
```
