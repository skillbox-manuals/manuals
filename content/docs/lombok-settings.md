---
title: "Использование Lombok"
weight: 200
---

Проект Lombok создан для уменьшения шаблонного (boilerplate) кода.

Ведь часто в классе нам требуется писать геттеры, сеттеры и конструкторы.
С помощью Lombok можно этот процесс автоматизировать и генерировать код
на этапе сборки проекта.

При этом кода на этапе разработки не существует и чтобы среда разработки
понимала, что код будет в дальнейшем существовать, необходимо настроить
проект для работы с Lombok.

🌍 А еще Lombok это имя острова в составе Индонезии, недалеко от Ява.

## 🛠️ Требования

Для использования Lombok ваш проект должен использовать:

- Java >= 1.8
- Maven 3.6.x (Gradle >= 4)

Также все действия будут проводиться в среде разработки IntelliJ IDEA.

## 📦 Добавление зависимостей в проект

В примере будет показан проект с использованием Maven и среды разработки
IntelliJ IDEA.

Добавьте в `pom.xml` зависимость:

```xml
<dependencies>
	<dependency>
		<groupId>org.projectlombok</groupId>
		<artifactId>lombok</artifactId>
		<version>1.18.24</version>
		<scope>provided</scope>
	</dependency>
</dependencies>
```

{{< hint info >}}
Область видимости `provided` говорит, что в результирующем артефакте
библиотеки Lombok не будет. Так как Lombok на этапе сборки создаст код
и более для работы приложения он не нужен.
{{< /hint >}}

Установите версию Java в pom.xml, в секцию `properties`. В таком случае Maven
будет использовать данную версию для компиляции проекта, если значение не установлено
будет по умолчанию использовать версия 1.5.

```xml
<properties>
    <maven.compiler.source>11</maven.compiler.source>
    <maven.compiler.target>11</maven.compiler.target>
</properties>
```

Примените изменения pom.xml, для этого используйте горячие клавиши: `Ctrl+Shift+O` / `⌘⇧I`
или обновите через контекстное меню папки проекта в Project вкладке и выберите `Maven -> Reload project`.

{{< hint info >}}
Если у вас версия IDEA выше 2020.3, то вам не требуется устанавливать дополнительные
плагины. Lombok плагин уже встроен в среду разработки.

В обратном случае установите плагин Lombok из магазина плагинов в настройках IDEA.
{{< /hint >}}

## ▶️ Использование

Сейчас посмотрим какие возможности нам дает Lombok на примере нескольких аннотаций.

### @Getter, @Setter

Нам часто приходиться создавать геттеры и сеттеры для полей класса. Lombok может
освободить от ручного создания таких методов и генерировать их при сборке проекта.

Если мы бы писали класс без использования Lombok:

```java
public class Person {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

Добавив над классов аннотации `@Getter`, `@Setter` мы получим точно такие же сеттеры,
названия методов по умолчанию формируется по соглашению getИмяПеременной, setИмяПеременной.

```java
@Getter
@Setter
public class Person {
    private String name;
    private int age;
}
```

Сеттеры генерируются только для не final полей. Геттеры для всех полей.

### @NoArgsConstructor, @AllArgsConstructor

Таким же образом, мы можем генерировать конструкторы класса. Допустим нашему классу необходимы
два конструктора: без аргументов и со всеми аргументами. Без Lombok мы напишем это так:

```java
@Getter
@Setter
public class Person {
    private String name;
    private int age;
    
    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
}
```

Добавив над классом аннотацию `@NoArgsConstructor` мы получим для
класса сгенерированный пустой конструктор:

```java
@Getter
@Setter
@NoArgsConstructor
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

}
```

И при использовании аннотации `@AllArgsConstructor`, Lombok создаст
конструктор для всех полей класса, аргументы будут располагаться
в порядке объявления полей внутри класса:

```java
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
public class Person {
    private String name;
    private int age;
}
```

Используя этот конструктор, мы напишем такую строку создания объекта
Person:

```java
Person person = new Person("Alex", 34);
```

### @ToString

Для переопределения метода toString() у класса, также можно
использовать Lombok. Аннотация на классом @ToString переопределит
метод и сформирует строку из всех полей класса и имени класса.

Например, если мы добавим к нашему классу Person аннотацию @ToString:

```java
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
@ToString
public class Person {
    private String name;
    private int age;
}
```

и после создадим объект и распечатаем его:

```java
Person person = new Person("Alex", 34);
System.out.println(person);
```

то получим в консоли строку:

```text
Person(name=Alex, age=34)
```

Не все поля нам нужны для toString и мы можем часть исключить, для этого
у аннотации есть дополнительный параметр exclude, в котором мы можем
прописать список полей, которые не участвуют в формировании строки. Это
полезно, когда нам надо скрыть чувствительные данные: пароли, персональные
данные, которые могут попасть в логи или в консоль.

```java
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
@ToString(exclude = {"age"})
public class Person {
    private String name;
    private int age;
}
```

И уже при печати не будет данных поля age:

```text
Person(name=Alex)
```

У других аннотаций также есть дополнительные параметрами, с которыми
при необходимости ознакомитесь в документации к Lombok.

### @Data

Есть аннотации, которые включают в себя другие аннотации, это позволяет
не писать множество аннотаций над классом, так как такие наборы аннотаций
часто повторяются и @Data позволяет нам одной строкой добавить к классу:

- `@ToString`
- `@Getter`
- `@Setter`
- `@RequiredArgsConstructor` - конструктор для всех final полей
- `@EqualsAndHashCode` - формирование методов equals() и hashCode() из всех полей

Для примера, заменим часть аннотаций в Person на `@Data`:

```java
@Data
@NoArgsConstructor
@AllArgsConstructor
public class Person {
    private String name;
    private int age;
}
```

Кода становиться меньше, но если нам требуется настроить более тонко
одну из аннотаций входящих в состав @Data, то необходимо ее написать
отдельно, например, чтобы исключить поля из toString()

```java
@Data
@NoArgsConstructor
@AllArgsConstructor
@ToString(exclude = {"age"})
public class Person {
    private String name;
    private int age;
}
```

## 📝 Документация по Lombok

У Lombok отличная и понятная документация, с примерами на
сайта проекта: <https://projectlombok.org/features/>
