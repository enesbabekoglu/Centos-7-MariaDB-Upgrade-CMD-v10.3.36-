# Centos-7-MariaDB-Upgrade-CMD-v10.3.36-

## ENGLISH
To update the MariaDB database to version 10.3.36 on a server with Linux Centos 7 operating system, these steps must be done in order.

**NOTE:** You must have root privileges to perform these operations.

We run the following commands on SSH, respectively.

-----------------------

**STEP 1**

We activate our root privilege.

```sudo su -```

-----------------------

**STEP 2**

We take backups of databases to avoid data loss. (Get yours to be safer if possible.)

```mysqldump -uadmin -P3306 -p"`cat /etc/psa/.psa.shadow`"  --all-databases > /tmp/all-database.sql```

-----------------------

**STEP 3**

```cp -a /var/lib/mysql/ /var/lib/mysql.bak```

-----------------------

**STEP 4**

We are stopping all our MariaDB and MySQL services.

```service mariadb stop```

-----------------------

**STEP 5**

We install the nano editor. If available, do not install.

```yum install -y nano```

-----------------------

**STEP 6**

We create a new file.

```nano -w /etc/yum.repos.d/MariaDB10.repo```

-----------------------

**STEP 7**

Save the code below to file.

**Save Steps**

1 - Copy with CTRL+C.

2 - Paste with CTRL+V.

3 - Apply the CTRL+X combination.

4 - Then type Y on the Yes/No screen

5 - Save changes by pressing CTRL+Enter.


```
# MariaDB 10.2 CentOS repository list - created 2016-01-18 09:58 UTC
# http://mariadb.org/mariadb/repositories/
[mariadb10.3]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
enabled=1
 
[mariadb10.2]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
enabled=0
```

-----------------------

**STEP 8**

We are installing the update.

```yum install mariadb -y```

-----------------------

**STEP 9**

We start our MySQL and MariaDB services.

```service mysql start```

-----------------------

## TÜRKÇE
Linux Centos 7 işletim sistemine sahip bir sunucuda MariaDB veritabanını versiyon 10.3.36 olarak güncellemek için sırasıyla bu adımlar yapılmalıdır.

**NOT:** Bu işlemleri gerçekleştirmek için root yetkisine sahip olmanız gerekir.

Sırasıyla SSH üzerinde aşağıdaki komutları çalıştırıyoruz.

-----------------------

**ADIM 1**

Root yetkimizi aktif ediyoruz.

```sudo su -```

-----------------------

**ADIM 2**

Veri kaybı olmaması için veri tabanlarının yedeklerini alıyoruz. (Mümkünse daha güvenli olması için kendinizde alın.)

```mysqldump -uadmin -P3306 -p"`cat /etc/psa/.psa.shadow`"  --all-databases > /tmp/all-database.sql```

-----------------------

**ADIM 3**

```cp -a /var/lib/mysql/ /var/lib/mysql.bak```

-----------------------

**ADIM 4**

Tüm MariaDB ve MySQL servislerimizi durduruyoruz.

```service mariadb stop```

-----------------------

**ADIM 5**

Nano düzenleyiciyi indiriyoruz. Sisteminizde kuruluysa yüklemeyin.

```yum install -y nano```

-----------------------

**ADIM 6**

Yeni bir dosya oluşturuyoruz.

```nano -w /etc/yum.repos.d/MariaDB10.repo```

-----------------------

**ADIM 7**

Aşağıdaki kodu dosyaya kaydedin.

**Kaydetme Adımları**

1 - CTRL+C ile kopyalayın.

2 - CTRL+V ile yapıştırın.

3 - CTRL+X kombinasyonunu uygulayın.

4 - Ardından Yes/No ekranında Y yazın.

5 - CTRL+Enter yaparak değişiklikleri kaydedin.


```
# MariaDB 10.2 CentOS repository list - created 2016-01-18 09:58 UTC
# http://mariadb.org/mariadb/repositories/
[mariadb10.3]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
enabled=1
 
[mariadb10.2]
name = MariaDB
baseurl = http://yum.mariadb.org/10.3/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
enabled=0
```

-----------------------

**ADIM 8**

Güncellemeyi yüklüyoruz.

```yum install mariadb -y```

-----------------------

**ADIM 9**

MySQL ve MariaDB servislerimizi başlatıyoruz.

```service mysql start```

-----------------------

