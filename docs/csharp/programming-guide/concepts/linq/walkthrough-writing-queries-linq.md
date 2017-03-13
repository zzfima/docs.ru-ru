---
title: "Walkthrough: Writing Queries in C# (LINQ) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], walkthroughs"
  - "LINQ [C#], writing queries"
  - "queries [LINQ in C#], writing"
  - "writing LINQ queries"
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Walkthrough: Writing Queries in C# (LINQ)
В этом пошаговом руководстве показано использование возможностей C\#, которые служат для написания выражений запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  После выполнения этого руководства можно переходить к примерам и документации по конкретным поставщикам [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], которые вас заинтересовали, например [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] в набор данных или [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Обязательные компоненты  
 В данном пошаговом руководстве требуется функции, представленные в Visual Studio 2008.  
  
 ![ссылка на видео](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Для просмотра видеоверсии этого раздела перейдите по ссылке [Видео: написание запросов в C\# \(LINQ\)](http://go.microsoft.com/fwlink/?LinkId=100393).  
  
## Создание проекта C\#  
  
#### Создание проекта  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  Разверните узел **Установлено**, разверните **Шаблоны**, разверните **Visual C\#**, а затем выберите **Консольное приложение**.  
  
4.  В текстовом поле **Имя** введите другое имя или примите имя по умолчанию, а затем нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5.  Обратите внимание, что проект содержит ссылку на System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=fullName>.  
  
## Создание расположенного в памяти источника данных  
 Источником данных для запросов является простой список объектов `Student`.  Каждая запись `Student` имеет имя, фамилию и массив целых чисел, представляющий результаты тестирования в классе.  Скопируйте этот код в проект.  Обратите внимание на следующие характеристики.  
  
-   Класс `Student` состоит из автоматически реализованных свойств.  
  
-   Каждый учащийся в списке инициализируется с помощью инициализатора объектов.  
  
-   Сам список инициализируется с помощью инициализатора коллекцией.  
  
 Вся эта структура данных будет инициализирована и создана без явных вызовов конструкторов или явного доступа к членам.  Дополнительные сведения об этих новых возможностях см. в разделах [Автоматически реализуемые свойства](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) и [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
#### Добавление источника данных  
  
-   Добавьте класс `Student` и инициализированный список учащихся к классу `Program` в проекте.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### Добавление нового учащегося в список учащихся  
  
1.  Добавьте нового `Student` в список `Students` и используйте любое имя и результаты тестирования.  Попробуйте набрать всю информацию о новом учащемся, чтобы лучше понять синтаксис инициализатора объектов.  
  
## Создание запроса  
  
#### Создание простого запроса  
  
-   В методе `Main` создайте простой запрос, который при выполнении вернет список всех учащихся, результат тестирования которых превысил 90 баллов.  Обратите внимание, что поскольку объект `Student` выбирается целиком, типом запроса будет `IEnumerable<Student>`.  Хотя код мог также использовать неявную типизацию при помощи ключевого слова [var](../../../../csharp/language-reference/keywords/var.md), используется явная типизация, чтобы ясно показать результаты.  Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
     Обратите внимание, что переменная диапазона запроса `student` служит ссылкой на каждый объект `Student` в источнике, предоставляя доступ к членам для каждого объекта.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## Выполнение запроса  
  
#### Для выполнения запроса:  
  
1.  Напишите цикл `foreach`, который приведет к выполнению запроса.  Обратите внимание на следующие моменты.  
  
    -   Доступ к каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации в цикле `foreach`.  
  
    -   Типом этой переменной является `Student`, а типом переменной запроса является совместимый `IEnumerable<Student>`.  
  
2.  После добавления этого кода выполните построение и запустите приложение, нажав сочетание клавиш Ctrl \+ F5 для просмотра результатов в окне **Консоль**.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### Добавление дополнительного условия фильтра  
  
1.  Чтобы уточнить запрос, можно объединить несколько логических условий в предложении `where`.  Следующий код добавляет условие таким образом, чтобы запрос возвращал тех учащихся, первый результат которых был более 90 баллов, а последний результат был меньше 80.  Предложение `where` должно выглядеть следующим образом.  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Дополнительные сведения см. в разделе [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## Изменение запроса  
  
#### Упорядочение результатов  
  
1.  Просматривать результаты легче, если они как\-то упорядочены.  Возвращаемую последовательность можно упорядочить по любому доступному полю в исходных элементах.  Например, следующее предложение `orderby` сортирует результаты в алфавитном порядке от А до Я по фамилии каждого учащегося.  Добавьте следующее предложение `orderby` к запросу, указав его после инструкции `where` и перед оператором `select`.  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  Теперь измените предложение `orderby` таким образом, чтобы оно сортировало результаты в обратном порядке по результату первого тестирования, от высшего к низшему показателю.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  Измените строку форматирования `WriteLine`, чтобы видеть результаты тестирования.  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### Группировка результатов  
  
1.  Группировка является мощной возможностью выражений запроса.  Запрос с предложением group создает последовательность групп, где каждая группа содержит `Key` и последовательность, состоящую из всех членов этой группы.  Следующий новый запрос группирует учащихся по первой букве их фамилии в качестве ключа.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  Обратите внимание, что тип запроса изменился.  Теперь он создает последовательность из групп, имеющих тип `char` в качестве ключа, и последовательность объектов `Student`.  Поскольку тип запроса изменился, следующий код изменяет также и цикл `foreach`.  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  Нажмите сочетание клавиш Ctrl \+ F5 для выполнения приложения и просмотра результатов в окне **Консоль**.  
  
     Дополнительные сведения см. в разделе [Предложение group](../../../../csharp/language-reference/keywords/group-clause.md).  
  
#### Присвоение переменной неявного типа  
  
1.  Явное кодирование `IEnumerables` из `IGroupings` может быстро стать трудоемким.  С помощью `var` можно более просто написать тот же запрос и цикл `foreach`.  Ключевое слово `var` не приводит к изменению типов объектов; оно просто сообщает компилятору о необходимости определения типов.  Измените тип `studentQuery` и переменная итерации `group` к `var` и повторно выполните запрос.  Обратите внимание, что во внутреннем цикле `foreach` переменная итерации по\-прежнему типизирована как `Student` и запрос работает так же, как и раньше.  Измените переменную итерации `s` на `var` и повторно выполните запрос.  Результаты остались неизменными.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     Более подробную информацию о [var](../../../../csharp/language-reference/keywords/var.md) см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
#### Упорядочение групп по значению их ключа  
  
1.  При выполнении предыдущего запроса группы были расположены не в алфавитном порядке.  Для упорядочения необходимо указать предложение `orderby` после предложения `group`.  Но, чтобы использовать предложение `orderby`, нужен идентификатор, служащий в качестве ссылки на группы, создаваемые предложением `group`.  Предоставить идентификатор можно с помощью ключевого слова `into` следующим образом.  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     При выполнении этого запроса группы будут отсортированы в алфавитном порядке.  
  
#### Введение идентификаторов с помощью let  
  
1.  Ключевое слово `let` можно использовать для представления идентификатора для любого результата выражения в выражении запроса.  Этот идентификатор может применяться для удобства, как в следующем примере, или он может повысить производительность, сохраняя результаты выражения так, чтобы оно не вычислялось повторно.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     Дополнительные сведения см. в разделе [Предложение let](../../../../csharp/language-reference/keywords/let-clause.md).  
  
#### Использование синтаксиса метода в выражении запроса  
  
1.  Как отмечалось в [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), некоторые операции запроса могут быть выражены только с помощью синтаксиса методов.  В следующем коде вычисляется общий результат для каждого `Student` в исходной последовательности, а затем вызывается метод `Average()`, использующий результаты запроса для вычисления среднего балла класса.  Обратите внимание на круглые скобки вокруг выражения запроса.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### Преобразование или проецирование в предложении select  
  
1.  Очень часто в запросах создаются последовательности, элементы которых отличаются от элементов в исходных последовательностях.  Удалите или закомментируйте предыдущий запрос и цикл и замените его следующим кодом.  Обратите внимание, что запрос возвращает последовательность строк \(не `Students`\), и этот факт отражается в цикле `foreach`.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  Приведенный ранее в этом пошаговом руководстве код показывает, что средний результат для всего класса составляет примерно 334.  Для создания последовательности `Students`, суммарный результат баллов которых больше среднего, вместе с их `Student ID`, можно использовать анонимный тип в инструкции `select`.  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## Следующие действия  
 После ознакомления с основными аспектами работы с запросами в C\# можно приступить к чтению документации и просмотру примеров для конкретного типа поставщика [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]:  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Пошаговое руководство. Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)