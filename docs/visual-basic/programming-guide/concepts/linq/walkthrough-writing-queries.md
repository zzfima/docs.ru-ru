---
title: "Пошаговое руководство. Написание запросов в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [LINQ в Visual Basic], написание"
  - "LINQ [Visual Basic], пошаговые руководства"
  - "LINQ [Visual Basic], написание запросов"
  - "написание запросов LINQ [Visual Basic]"
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 68
---
# Пошаговое руководство. Написание запросов в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом пошаговом руководстве показано использование возможностей Visual Basic для написания выражений запросов [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)].  Это руководство показывает процесс создания запросов к списку объектов Student, их выполнение и изменение.  Запросы включают в себя несколько функций, которые были новыми в Visual Basic 2008, в том числе инициализаторы объектов, вывод локального типа и анонимные типы.  
  
 После выполнения этого пошагового руководства можно переходить к примерам и документации по конкретным интересующим вас поставщикам [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  К поставщикам [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] относятся [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)] и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Создание проекта  
  
#### Создание проекта консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
3.  В списке **Установленные шаблоны** щелкните **Visual Basic**.  
  
4.  В списке типов проекта выберите **Консольное приложение**.  В поле **Имя** введите имя проекта и нажмите кнопку **ОК**.  
  
     Проект создан.  По умолчанию он содержит ссылку на System.Core.dll.  Кроме того, список **Импортируемые пространства имен** в [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic) включает пространство имен <xref:System.Linq?displayProperty=fullName>.  
  
5.  На [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** имеет значение **На**.  
  
## Добавление находящегося в памяти источника данных  
 Источником данных для запросов в этом руководстве является список объектов `Student`.  Каждый объект `Student` содержит имя, фамилию, год обучения и академическую успеваемость.  
  
#### Добавление источника данных  
  
-   Определите класс `Student` и создайте список экземпляров класса.  
  
    > [!IMPORTANT]
    >  Код, необходимый для определения класса `Student` и создания списка, используемого в примерах, приведен в разделе [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  Можно скопировать его оттуда и вставить в проект.  Новый код заменяет код, появившийся при создании проекта.  
  
#### Добавление нового студента в список студентов  
  
-   Для добавления в список другого экземпляра класса `Student` следуйте шаблону в методе `getStudents`.  После добавления учащегося будут представлены инициализаторы объектов.  Дополнительные сведения см. в разделе [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## Создание запроса  
 При выполнении созданного в этом разделе запроса выводится список студентов, успеваемость которых попадает в десятку лучших.  Поскольку запрос каждый раз выбирает завершенные объекты `Student`, типом результата запроса является `IEnumerable(Of Student)`.  Однако в определениях запроса тип запроса обычно не указывается.  Вместо этого компилятор использует локальное определение типа.  Дополнительные сведения см. в разделе [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  Переменная диапазона запроса, `currentStudent`, служит в качестве ссылки на каждый экземпляр `Student` в источнике `students`, предоставляя доступ к свойствам каждого объекта в `students`.  
  
#### Создание простого запроса  
  
1.  Найдите в методе `Main` проекта место, которое помечено следующим образом.  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_1.vb)]  
  
     Скопируйте следующий код и вставьте его.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_2.vb)]  
  
2.  Наведите указатель мыши на `studentQuery` в коде, чтобы проверить, что компилятор назначил тип `IEnumerable(Of Student)`.  
  
## Выполнение запроса  
 Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса.  Типичным механизмом выполнения запроса является цикл `For Each`.  Доступ к каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации цикла.  Дополнительные сведения о выполнении запроса см. в разделе [Написание первого запроса LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### Выполнение запроса  
  
1.  Добавьте следующий цикл `For Each` под запросом в проекте.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_3.vb)]  
  
2.  Наведите указатель мыши на переменную цикла `studentRecord` для просмотра ее типа данных.  Тип `studentRecord` определен как `Student`, поскольку `studentQuery` возвращает коллекцию экземпляров `Student`.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL \+ F5.  Обратите внимание на результаты в окне консоли.  
  
## Изменение запроса  
 Результаты запроса легче просматривать, если они упорядочены.  Возвращаемую последовательность можно отсортировать по любому доступному полю.  
  
#### Упорядочение результатов  
  
1.  Добавьте следующее предложение `Order By` между операторами `Where` и `Select` в запросе.  Предложение `Order By` будет упорядочивать результаты в алфавитном порядке от А до Я по фамилиям студентов.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Чтобы упорядочить сначала по фамилии, а затем по имени, добавьте в запрос оба поля.  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Чтобы упорядочить от Я до А, можно также указать `Descending`.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL \+ F5.  Обратите внимание на результаты в окне консоли.  
  
#### Ввод локального идентификатора  
  
1.  Чтобы ввести локальный идентификатор в выражение запроса, добавьте код в данном разделе.  Локальный идентификатор будет содержать промежуточные результаты.  В следующем примере `name` является идентификатором, который содержит сочетание имени и фамилии студента.  Локальный идентификатор может использоваться для удобства либо он может повысить производительность, сохраняя результаты выражения, которые в противном случае пришлось бы вычислять несколько раз.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_4.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL \+ F5.  Обратите внимание на результаты в окне консоли.  
  
#### Проецирование одного поля в предложении Select  
  
1.  Добавьте запрос и цикл `For Each` из этого раздела, чтобы создать запрос, выводящий последовательность, элементы которой отличаются от элементов источника.  В следующем примере источником является коллекция объектов `Student`, однако возвращается только один член каждого объекта: имена студентов, фамилия которых Орехов.  Поскольку `currentStudent.First` является строкой, типом данных последовательности, возвращаемой `studentQuery3`, является последовательность строк `IEnumerable(Of String)`.  Как и в предыдущих примерах, назначение типа данных для `studentQuery3` предоставлено компилятору, который будет использовать локальное определение типа.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_5.vb)]  
  
2.  Наведите указатель мыши на `studentQuery3` в коде, чтобы проверить, что компилятор назначил тип `IEnumerable(Of String)`.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL \+ F5.  Обратите внимание на результаты в окне консоли.  
  
#### Создание анонимного типа в предложении Select  
  
1.  Добавьте код из этого раздела, чтобы просмотреть использование анонимных типов в запросах.  Их можно использовать в запросах при необходимости возвращать несколько полей из источника данных, вместо полных записей \(записи `currentStudent` в предыдущих примерах\) или единичных полей \(`First` в предыдущем разделе\).  Вместо указания новый именованный тип, содержащий поля, которые требуется включить в результат задайте поля в предложении `Select` и компилятор создает анонимный тип с этими полями как свойства. Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     В следующем примере создается запрос, возвращающий имя и успеваемость старшекурсников, чья успеваемость находится между 1 и 10 в порядке успеваемости.  В этом примере необходимо определить тип `studentQuery4`, поскольку предложение `Select` возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_6.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL \+ F5.  Обратите внимание на результаты в окне консоли.  
  
## Дополнительные примеры  
 Теперь, обладая основными знаниями, можно просмотреть приведенный ниже список дополнительных примеров, который иллюстрирует гибкость и мощь запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Каждый пример содержит краткое описание выполняемых действий.  Создать через переменную результата запроса для каждого запроса, чтобы просмотреть определенный тип. Используйте цикл `For Each`, чтобы получить.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_7.vb)]  
  
## Дополнительные сведения  
 После ознакомления с основными принципами работы с запросами, можно приступить к чтению документации и просмотру примеров для конкретного типа интересующего вас поставщика [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)