---
title: Написание запросов
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6d2e472cc996c42aa091ed95c6954d0879c98372
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636761"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Пошаговое руководство. Написание запросов в Visual Basic

В этом пошаговом руководстве показано, как можно использовать функции языка Visual Basic для написания выражений запросов LINQ. В этом пошаговом руководстве показано, как создавать запросы к списку объектов Student, выполнять запросы и изменять их. Запросы включают в себя несколько функций, включая инициализаторы объектов, определение локального типа и анонимные типы.

После завершения этого пошагового руководства вы будете готовы перейти к образцам и документации для конкретного интересующего поставщика LINQ. Поставщики LINQ включают [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].

## <a name="create-a-project"></a>Создание проекта

### <a name="to-create-a-console-application-project"></a>Создание проекта консольного приложения

1. Запустите Visual Studio.

2. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

3. В списке **Установленные шаблоны** щелкните **Visual Basic**.

4. В списке типов проектов щелкните **консольное приложение**. В поле **имя** введите имя проекта и нажмите кнопку **ОК**.

    Создается проект. По умолчанию он содержит ссылку на библиотеку System. Core. dll. Кроме того, список **импортированных пространств имен** на [странице ссылки в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) включает пространство имен <xref:System.Linq?displayProperty=nameWithType>.

5. На [странице Компиляция в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)убедитесь, что **параметр Infer** имеет значение **On**.

## <a name="add-an-in-memory-data-source"></a>Добавление источника данных в памяти

Источником данных для запросов в этом пошаговом руководстве является список объектов `Student`. Каждый объект `Student` содержит имя, фамилию, класс year и академический рейтинг в тексте учащегося.

### <a name="to-add-the-data-source"></a>Добавление источника данных

- Определите класс `Student` и создайте список экземпляров класса.

  > [!IMPORTANT]
  > Код, необходимый для определения класса `Student` и создания списка, используемого в примерах пошагового руководства, приведен в разделе [Практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Вы можете скопировать его из него и вставить в проект. Новый код заменяет код, который отображался при создании проекта.

### <a name="to-add-a-new-student-to-the-students-list"></a>Добавление нового учащегося в список учащихся

- Используйте шаблон в методе `getStudents`, чтобы добавить в список другой экземпляр `Student` класса. При добавлении учащегося будут представлены инициализаторы объектов. Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Создание запроса

При выполнении запроса, добавленного в этом разделе, создается список учащихся, чьи учебные заведения помещают в десять первых. Поскольку запрос выбирает полный `Student`ный объект каждый раз, тип результата запроса `IEnumerable(Of Student)`. Однако тип запроса обычно не указывается в определениях запросов. Вместо этого компилятор использует определение локального типа для определения типа. Дополнительные сведения см. в разделе [определение локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Переменная диапазона запроса, `currentStudent`, служит ссылкой на каждый экземпляр `Student` в источнике, `students`, предоставляя доступ к свойствам каждого объекта в `students`.

### <a name="to-create-a-simple-query"></a>Создание простого запроса

1. Найдите место в методе `Main` проекта, который помечен следующим образом:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Скопируйте приведенный ниже код и вставьте его в.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Наведите указатель мыши на `studentQuery` в коде, чтобы убедиться, что назначенный компилятором тип `IEnumerable(Of Student)`.

## <a name="run-the-query"></a>Выполнение запроса

Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса. Типичным механизмом выполнения запроса является цикл `For Each`. Доступ к каждому элементу в возвращаемой последовательности осуществляется через переменную итерации цикла. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>Выполнение запроса

1. Добавьте следующий цикл `For Each` под запросом в проекте.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Наведите указатель мыши на переменную управления цикла `studentRecord`, чтобы увидеть ее тип данных. Тип `studentRecord` выводится `Student`, поскольку `studentQuery` Возвращает коллекцию экземпляров `Student`.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="modify-the-query"></a>Изменение запроса

Проще проверять результаты запроса, если они находятся в указанном порядке. Возвращаемую последовательность можно отсортировать на основе любого доступного поля.

### <a name="to-order-the-results"></a>Упорядочение результатов

1. Добавьте следующее предложение `Order By` между оператором `Where` и инструкцией `Select` запроса. Предложение `Order By` упорядочивает результаты в алфавитном порядке от A до Z в соответствии с фамилией каждого учащегося.

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. Чтобы упорядочить по фамилии, а затем по имени, добавьте в запрос оба поля:

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    Можно также указать `Descending`, чтобы упорядочить от я до а.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-introduce-a-local-identifier"></a>Введение локального идентификатора

1. Добавьте код в этом разделе, чтобы ввести локальный идентификатор в выражение запроса. Локальный идентификатор будет содержать промежуточный результат. В следующем примере `name` — это идентификатор, содержащий объединение имени и фамилии учащегося. Локальный идентификатор можно использовать для удобства или повысить производительность, сохранив результаты выражения, которые в противном случае будут вычисляться несколько раз.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-project-one-field-in-the-select-clause"></a>Проецирование одного поля в предложении SELECT

1. Добавьте запрос и `For Each` цикл из этого раздела, чтобы создать запрос, создающий последовательность, элементы которой отличаются от элементов в источнике. В следующем примере источником является коллекция объектов `Student`, но возвращается только один элемент каждого объекта: имя учащихся, чье фамилия — Гарсиа. Поскольку `currentStudent.First` является строкой, тип данных последовательности, возвращаемой `studentQuery3`, — это `IEnumerable(Of String)`последовательность строк. Как и в предыдущих примерах, назначение типа данных для `studentQuery3` оставлено компилятору для определения с помощью определения локального типа.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Наведите указатель мыши на `studentQuery3` в коде, чтобы убедиться, что назначенный тип `IEnumerable(Of String)`.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Создание анонимного типа в предложении SELECT

1. Добавьте код из этого раздела, чтобы увидеть, как анонимные типы используются в запросах. Они используются в запросах, если требуется вернуть несколько полей из источника данных, а не полные записи (`currentStudent` записи в предыдущих примерах) или отдельные поля (`First` в предыдущем разделе). Вместо определения нового именованного типа, содержащего поля, которые необходимо включить в результат, необходимо указать поля в предложении `Select`, и компилятор создаст анонимный тип с этими полями в качестве свойств. Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

    В следующем примере создается запрос, который возвращает имя и звание старших званий, чьи учебные заведения находятся в диапазоне от 1 до 10 в порядке академических званий. В этом примере тип `studentQuery4` должен быть определен, поскольку предложение `Select` возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="additional-examples"></a>Дополнительные примеры

Теперь, когда вы понимаете основы, ниже приведен список дополнительных примеров для демонстрации гибкости и возможностей запросов LINQ. Каждому примеру предшествует краткое описание того, что он делает. Наведите указатель мыши на переменную результата запроса для каждого запроса, чтобы увидеть выведенный тип. Для получения результатов используйте цикл `For Each`.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Дополнительные сведения

После ознакомления с основными понятиями работы с запросами вы можете ознакомиться с документацией и примерами для конкретного типа поставщика LINQ, который вас интересует:

- [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>См. также:

- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
