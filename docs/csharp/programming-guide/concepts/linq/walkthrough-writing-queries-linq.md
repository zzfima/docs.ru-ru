---
title: "Пошаговое руководство. Написание запросов на C# (LINQ)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aef03dca681f0b3d24f2ab55eef4ae29ee515132
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-writing-queries-in-c-linq"></a>Пошаговое руководство. Написание запросов на C# (LINQ)
В этом пошаговом руководстве описываются возможности C#, предназначенные для написания выражений запросов LINQ.  
  
## <a name="create-a-c-project"></a>Создание проекта C#  
  
> [!NOTE]
>  Приведенные ниже инструкции относятся к Visual Studio. Если вы пользуетесь другой средой разработки, создайте консольный проект со ссылкой на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=fullName>.  
  
#### <a name="to-create-a-project-in-visual-studio"></a>Создание проекта в Visual Studio  
  
1.  Запустите Visual Studio.  
  
2.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#**, а затем выберите **Консольное приложение**.  
  
4.  В текстовое поле **Имя** введите другое имя или примите имя по умолчанию и нажмите кнопку **ОК**.  
  
     В **обозревателе решений** появится новый проект.  
  
5.  Обратите внимание, что проект содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен <xref:System.Linq?displayProperty=fullName>.  
  
## <a name="create-an-in-memory-data-source"></a>Создание источника данных в памяти  
 Источником данных для запросов является простой список объектов `Student`. Каждая запись `Student` включает имя, фамилию и массив целых чисел, соответствующих их баллам за проведенные в классе тесты. Скопируйте этот код в проект. Обратите внимание на следующие характеристики.  
  
-   Класс `Student` состоит из автоматически внедренных свойств.  
  
-   Каждый учащийся в списке инициализируется соответствующим инициализатором объекта.  
  
-   Сам список инициализируется инициализатором коллекции.  
  
 Вся эта структура данных инициализируется и создается без явных вызовов какого-либо конструктора или прямого доступа к членам. Дополнительные сведения об этих новых возможностях см. в разделах [Автоматически внедренные свойства](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) и [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
#### <a name="to-add-the-data-source"></a>Добавление источника данных  
  
-   Добавьте класс `Student` и инициализированный список учащихся в класс `Program` в проекте.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Добавление нового учащегося в список учащихся  
  
1.  Добавьте новый объект `Student` в список `Students` и введите любое имя и результаты тестирования. Чтобы лучше изучить синтаксис инициализатора объекта, постарайтесь заполнить все данные нового учащегося.  
  
## <a name="create-the-query"></a>Создание запроса  
  
#### <a name="to-create-a-simple-query"></a>Создание простого запроса  
  
-   В методе `Main` приложения создайте простой запрос, при выполнении которого будет возвращаться список учащихся, набравших в результате тестирования больше 90 баллов. Поскольку выбран весь объект `Student`, запрос имеет тип `IEnumerable<Student>`. Несмотря на то, что код можно также набрать напрямую, используя ключевое слово [var](../../../../csharp/language-reference/keywords/var.md), для демонстрации результатов применяется неявная типизация. (Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)  
  
     Кроме того переменная диапазона в запросе, `student`, служит ссылкой на каждый объект `Student` в источнике и предоставляет доступ к каждому объекту.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## <a name="execute-the-query"></a>Выполнение запроса  
  
#### <a name="to-execute-the-query"></a>Порядок выполнения запроса  
  
1.  Теперь напишите цикл `foreach`, вызывающий выполнение запроса. Обратите внимание на следующие моменты:  
  
    -   Доступ к каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации в цикле `foreach`.  
  
    -   Эта переменная имеет тип `Student`, а переменная запроса — совместимый тип `IEnumerable<Student>`.  
  
2.  Добавив код, соберите и запустите приложение, чтобы отобразить результаты в окне **Консоль**.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### <a name="to-add-another-filter-condition"></a>Добавление другого условия фильтра  
  
1.  Чтобы сделать запрос более точным, можно объединить несколько логических условий в предложение `where`. Следующий код добавляет условие, согласно которому запрос возвращает учащихся, которые по первому тесту набрали больше 90 баллов, а по второму — меньше 80 баллов. Предложение `where` должно быть аналогично приведенному ниже коду.  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Дополнительные сведения см. в разделе [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## <a name="modify-the-query"></a>Изменение запроса  
  
#### <a name="to-order-the-results"></a>Упорядочение результатов  
  
1.  С результатами проще работать, если они упорядочены. Возвращаемую последовательность можно упорядочить по любому доступному полю в исходных элементах. Например, следующее предложение `orderby` упорядочивает результаты в алфавитном порядке от А до Z, используя фамилии учащихся. Добавьте к запросу следующее предложение `orderby`, указав его после оператора `where` и перед оператором `select`:  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  Теперь измените предложение `orderby` таким образом, чтобы результаты были упорядочены по баллам за первый тест в обратном порядке, от наибольшего к наименьшему.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  Измените строку формата `WriteLine` таким образом, чтобы отобразить баллы:  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### <a name="to-group-the-results"></a>Группировка результатов  
  
1.  Группировка представляет собой полезную возможность в выражениях запросов. Запрос с предложением group создает последовательность групп, в которой каждая группа содержит `Key`, и последовательность, состоящую из всех членов этой группы. Представленный ниже запрос группирует учащихся, используя в качестве ключа первую букву фамилии.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  Обратите внимание на то, что тип запроса изменился. Теперь он создает последовательность групп с типом `char` в качестве ключа и последовательность объектов `Student`. Поскольку тип запроса изменился, следующий код изменяет также цикл выполнения `foreach`:  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  Запустите приложение и просмотрите результаты в окне **Консоль**.  
  
     Дополнительные сведения см. в разделе [Предложение group](../../../../csharp/language-reference/keywords/group-clause.md).  
  
#### <a name="to-make-the-variables-implicitly-typed"></a>Преобразование переменных в явно типизированные  
  
1.  Набирать код `IEnumerables` в `IGroupings` напрямую — далеко не самое увлекательное занятие. Написать тот же запрос и цикл `foreach` можно быстрее и проще, воспользовавшись переменной `var`. Ключевое слово `var` не приводит к изменению типов объектов, оно просто сообщает компилятору о том, что он должен вывести типы логически. Измените тип `studentQuery` и переменную итерации `group` на `var` и выполните запрос заново. Обратите внимание на то, что во внутреннем цикле `foreach` переменная итерации по-прежнему типизируется как `Student`, а запрос работает так же, как раньше. Измените переменную итерации `s` на `var` и выполните запрос заново. Результаты будут точно такими же.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     Дополнительные сведения о переменной [var](../../../../csharp/language-reference/keywords/var.md) см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
#### <a name="to-order-the-groups-by-their-key-value"></a>Упорядочение групп по значению ключа  
  
1.  Выполняя предыдущий запрос, вы могли заметить, что группы отображаются не в алфавитном порядке. Для того чтобы это изменить, необходимо указать предложение `orderby` после предложения `group`. Но, чтобы использовать предложение `orderby`, нужен идентификатор, служащий в качестве ссылки на группы, создаваемые предложением `group`. Укажите идентификатор с помощью ключевого слова `into`, как показано ниже:  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     После выполнения этого запроса группы будут отсортированы в алфавитном порядке.  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a>Введение идентификаторов с помощью предложения let  
  
1.  Ключевое слово `let` позволяет ввести идентификатор для любого результата в выражении запроса. Этот идентификатор может применяться для удобства, как в следующем примере, или повышать производительность, сохраняя результаты выражения, чтобы не вычислять их повторно.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     Дополнительные сведения см. в разделе [Предложение let](../../../../csharp/language-reference/keywords/let-clause.md).  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a>Использование синтаксиса метода в выражении запроса  
  
1.  Как описано в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), некоторые операции запросов можно выразить, только используя синтаксис метода. Представленный ниже код вычисляет общий балл для каждого объекта `Student` в исходной последовательности, а затем применяет метод `Average()` к результатам запроса, чтобы рассчитать средний балл класса. Обратите внимание на то, что выражение запроса заключено в круглые скобки.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a>Преобразование или проецирование в предложение select  
  
1.  Запрос очень часто выдает последовательность, элементы которой отличаются от элементов в исходной последовательности. Удалите или закомментируйте предыдущий запрос и цикл выполнения и замените его на представленный ниже код. Обратите внимание на то, что запрос возвращает последовательность строк (не `Students`), и этот факт отражается в цикле `foreach`.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  Код, представленный выше в этом пошаговом руководстве, показывает, что среднее количество баллов по классу составляет около 334. Для создания последовательности `Students`, сумма баллов в которой будет выше, чем средний показатель по классу, с указанием `Student ID` можно вставить в оператор `select` анонимный тип:  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Ознакомившись с основными аспектами работы с запросами в C#, вы будете готовы прочитать документацию и примеры по интересующему вас типу поставщика LINQ:  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>См. также  
 [LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)   
 [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)

