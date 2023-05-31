# Втора лабораториска вежба по предметот Софтверско инженерство

## Име и презиме: Зорица Ников 
## Број на индекс: 216150

### 2. Фотографија од кодот на функцијата и Control Flow графот
Кодот на функцијата со додадени коментари кои ги обележуваат јазлите на дијаграмот

![Kod](https://github.com/finkash/SI_2023_lab2_216150/assets/108621007/74989057-1a4a-4259-a72f-1f23f00bb7e8)

Дијаграмот

![Diagram](https://github.com/finkash/SI_2023_lab2_216150/assets/108621007/73d81b51-a196-4a66-8d51-b52396049151)


### 3. Цикломатската комплекснот на графот
#### Цикломатската комплексност на графот е 11.
#### Таа е добиена на следниот начин: 37 - 28 + 2 * 1
Формула која се користи: Број на ребра - број на јазли + 2 * број на поврзани компоненти
   
### 4. Тест случаи според критериумот Every branch 

#### 1 test-case) 
Со повикот на `function(null, allUsers)` со вредност `null` за параметарот `user` ќе се фрли `RuntimeException` и извршувањето на функцијата ќе се прекине во овој момент. Параметарот `allUsers` не е релевантен во овој случај.

`function(null, allUsers)`

#### 2 test-case)
Бидејќи `user` објектот има `username` со вредност `null`, ќе се премине на линија 4 каде што ќе се постави `username`-oт да има иста вредност како и `email`. Потоа, ќе се провери if-условот на линија 6. Овој услов проверува дали `user` има валидна e-mail адреса, па ќе се влезе во if-блокот на линија 7. 
Внатре ќе се изврши for-циклусот на линија 8. Се пристапува до секој објект од `allUsers` листата и се проверува дали e-mail адресата или корисничкото име на `user` се совпаѓаат со веќе постоечките корисници. Потоа, се променуваат променливите `specialCharacters`, `password`, и `passwordLower` на линиите 14, 15 и 16.
На крај, се проверува условот на линија 17. Во овој случај, `passwordLower` го содржи username-от zoricanikov@yahoo.com во себе, па условот е исполнет. Функцијата ќе врати `false` на линија 18.

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
Влезниот објект има непразен `user` со непразни `username`, `password` и `email`. Исто така, кодот нема да влезе во if-условот на линија 3, и `username` ќе остане ист. Е-поштата "zoricanikov" не е валидна и кодот нема да влезе во if-блокот на линија 7, па со тоа ќе го прескокне и for-циклусот на линија 8. Променливите `specialCharacters`, `password` и `passwordLower` ќе бидат иницијализирани на линиите 14, 15 и 16 соодветно. Условот на линија 17 нема да се исполни. Кодот ќе оди на линија 19, но бидејќи `password` содржи празно место, нема да влезе внатре во линија 20, туку ќе оди на линија 23 и функцијата ќе врати `false`.


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
Се е исто со претходниот тест случај со разлика само во тоа што `password` не содржи празно место и кодот ќе влезе во линија 20 и со for-циклусот ќе се проверува дали содржи специјален знак и бидејќи содржи специјален знак, кодот ќе влезе во линија 22 и ќе ја врати вредноста на променливата `same`, а таа е 0.
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

#### 5 test-case)
Исто и овде, кодот ќе влезе во if-блокот на линија 19 бидејќи `passwordLower` не содржи празно место. Циклусот на линија 20 ќе проверува дали `password` содржи некој специјален знак, но бидејќи не содржи никогаш нема да влезе во линија 22, ќе се излезе од for-циклусот и функцијата ќе врати `false`. 
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
Во тест случаите 1,3,4 и 5, листата на Users односно какви им се `username`, `password` и `email` на другите корисници не е релевантно бидејќи тие не се проверуваат.
Заклучуваме дека за да се поминат сите branches во кодот, минимум се потребни 5 тест случаи. 

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
Четвртиот и последен случај е кога и трите услови се невистинити (после првиот мора да се провери вториот, и после од кога се заклучува дека вториот е невистинит, мора да се провери и третиот).

пример:
 - user != null, password == lozinka123, email == zorica.nikov@yahoo.com
