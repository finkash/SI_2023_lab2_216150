# Втора лабораториска вежба по предметот Софтверско инженерство

## Име и презиме: Зорица Ников 
## Број на индекс: 216150

### 2. Фотографија од Control Flow графот
Кодот на функцијата со додадени коментари кои ги обележуваат јазлите на дијаграмот

![Kod](https://github.com/finkash/SI_2023_lab2_216150/assets/108621007/74989057-1a4a-4259-a72f-1f23f00bb7e8)

![Diagram](https://github.com/finkash/SI_2023_lab2_216150/assets/108621007/73d81b51-a196-4a66-8d51-b52396049151)


### 3. Цикломатската комплекснот на графот е: 11
   Таа е добиена на следниот начин: 37 - 28 + 2 * 1 
   Формула: Број на ребра - број на јазли + 2 * број на поврзани компоненти
   
### 4. Тест случаи според критериумот Every branch 

#### 1 test-case) 
`function(null, allUsers)`

#### 2 test-case)

```
function(
  {
    username: null,
    password: zoricanikov@yahoo.com,
    email: zoricanikov@yahoo.com
  },
    
  {
    {
      username: stefanija,
      password: 93824jfsfjsd,
      email: zoricanikov@yahoo.com
    },
    {
      username: zoricanikov@yahoo.com
      password: 98301192u4,
      email: angelanikolova@yahoo.com
    }
  }
)
```

#### 3 test-case)
```
function(
  {
    username: nikovzorica,
    password: 1234 567890,
    email: zoricanikov
  },
    
  {
    {
      username: stefanija,
      password: 93824jfsfjsd,
      email: zoricanikov@yahoo.com
    },
    {
      username: zoricanikov@yahoo.com
      password: 98301192u4,
      email: angelanikolova@yahoo.com
    }
  }
)
```

#### 4 test-case)
```
function(
  {
    username: nikovzorica,
    password: 12345#7890,
    email: zoricanikov
  },
    
  {
    {
      username: stefanija,
      password: 93824jfsfjsd,
      email: zoricanikov@yahoo.com
    },
    {
      username: zoricanikov@yahoo.com
      password: 98301192u4,
      email: angelanikolova@yahoo.com
    }
  }
)
```

5 test-case)
```
function(
  {
    username: nikovzorica,
    password: 123457890,
    email: zoricanikov
  },
    
  {
    {
      username: stefanija,
      password: 93824jfsfjsd,
      email: zoricanikov@yahoo.com
    },
    {
      username: zoricanikov@yahoo.com
      password: 98301192u4,
      email: angelanikolova@yahoo.com
    }
  }
)
```

### 5. Тест случаи според Multiple Condition критериумот 

Тест случаи според Multiple Condition критериумот за условот: `if (user==null || user.getPassword()==null || user.getEmail()==null)`.

#### 1) T || X || X
Првиот случај е кога првиот услов е вистинит, а вистинитоста на другите два услова не е важна, бидејќи нема да се проверуваат.

примери: 
 - user == null, password == lozinka123, email == null
 - user == null, password == null, email == zorica.nikov@yahoo.com
 - user == null, password == null, email == null
 - user == null, password == lozinka123, email == zorica.nikov@yahoo.com

#### 2) F || T || X
Вториот случај е кога првиот услов е невистинит (се проверува вториот случај) и кога вториот случај е вистинит, вистинитоста на третиот услов не е важна, и не се проверува.

примери:
 - user != null, password == null, email == null
 - user != null, password == null, email == zorica.nikov@yahoo.com

#### 3) F || F || T
Tретиот случат е кога првиот и вториот услов се невистинити (вториот мора да се провери), и третиот случај(исто така мора да се провери) е вистинит.

пример:
 - user != null, password == lozinka123, email == null

#### 4) F || F || F
Четвртиот и последен случај е кога и трите услови се невистинити (после првиот мора да се провери вториот, и после од кога се заклучува дека вториот е невистинит, мора да се провери и третиот)

пример:
 - user != null, password == lozinka123, email == zorica.nikov@yahoo.com
