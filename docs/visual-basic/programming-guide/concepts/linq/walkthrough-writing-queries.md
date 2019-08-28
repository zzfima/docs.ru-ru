---
title: Создание запросов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 256075ad5de5b88595dd4be7f199a74b5912c082
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046548"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Пошаговое руководство. Создание запросов в Visual Basic

В этом пошаговом руководстве показано, как можно использовать функции [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] языка Visual Basic для написания выражений запросов. В этом пошаговом руководстве показано, как создавать запросы к списку объектов Student, выполнять запросы и изменять их. Запросы включают в себя несколько функций, включая инициализаторы объектов, определение локального типа и анонимные типы.

После завершения этого пошагового руководства вы будете готовы перейти к образцам и документации для конкретного [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] интересующего вас поставщика. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]поставщики включают [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].

## <a name="create-a-project"></a>Создание проекта

### <a name="to-create-a-console-application-project"></a>Создание проекта консольного приложения

1. Запустите Visual Studio.

2. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

3. В списке **Установленные шаблоны** щелкните **Visual Basic**.

4. В списке типов проектов щелкните **консольное приложение**. В поле **имя** введите имя проекта и нажмите кнопку **ОК**.

    Создается проект. По умолчанию он содержит ссылку на библиотеку System. Core. dll. Кроме того, в списке **Импортированные пространства имен** на [странице ссылки в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) содержится <xref:System.Linq?displayProperty=nameWithType> пространство имен.

5. На [странице Компиляция в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)убедитесь, что **параметр Infer** имеет значение **On**.

## <a name="add-an-in-memory-data-source"></a>Добавление источника данных в памяти

Источником данных для запросов в этом пошаговом руководстве является список `Student` объектов. Каждый `Student` объект содержит имя, фамилию, класс year и академический рейтинг в тексте учащегося.

### <a name="to-add-the-data-source"></a>Добавление источника данных

- `Student` Определите класс и создайте список экземпляров класса.

  > [!IMPORTANT]
  > Код, необходимый для определения `Student` класса и создания списка, используемого в примерах пошагового руководства, приведен в разделе [практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Вы можете скопировать его из него и вставить в проект. Новый код заменяет код, который отображался при создании проекта.

### <a name="to-add-a-new-student-to-the-students-list"></a>Добавление нового учащегося в список учащихся

- Следуйте шаблону в `getStudents` методе, чтобы добавить в список другой `Student` экземпляр класса. При добавлении учащегося будут представлены инициализаторы объектов. Дополнительные сведения см. в [разделе Инициализаторы объектов: Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Создание запроса

При выполнении запроса, добавленного в этом разделе, создается список учащихся, чьи учебные заведения помещают в десять первых. Поскольку запрос выбирает полный `Student` объект каждый раз, тип результата запроса —. `IEnumerable(Of Student)` Однако тип запроса обычно не указывается в определениях запросов. Вместо этого компилятор использует определение локального типа для определения типа. Дополнительные сведения см. в разделе [определение локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Переменная `currentStudent`диапазона запроса, выступает в качестве ссылки на каждый `Student` `students`экземпляр в источнике, предоставляя доступ к свойствам каждого объекта в `students`.

### <a name="to-create-a-simple-query"></a>Создание простого запроса

1. Найдите место в `Main` методе проекта, который помечен следующим образом:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Скопируйте приведенный ниже код и вставьте его в.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Наведите указатель `studentQuery` мыши на код, чтобы убедиться, что назначенный компилятором тип имеет `IEnumerable(Of Student)`значение.

## <a name="run-the-query"></a>Выполнение запроса

Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса. Типичный механизм выполнения запроса — `For Each` цикл. Доступ к каждому элементу в возвращаемой последовательности осуществляется через переменную итерации цикла. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>Выполнение запроса

1. Добавьте следующий `For Each` цикл под запросом в проекте.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Наведите указатель мыши на переменную `studentRecord` управления циклом, чтобы увидеть ее тип данных. Тип `studentRecord` выводится `Student` как,`studentQuery` так как Возвращает коллекцию экземпляров.`Student`

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="modify-the-query"></a>Изменение запроса

Проще проверять результаты запроса, если они находятся в указанном порядке. Возвращаемую последовательность можно отсортировать на основе любого доступного поля.

### <a name="to-order-the-results"></a>Упорядочение результатов

1. Добавьте следующее `Order By` предложение `Where` между оператором и `Select` инструкцией запроса. `Order By` Предложение упорядочивает результаты в алфавитном порядке от A до Z в соответствии с фамилией каждого учащегося.

    ```
    Order By currentStudent.Last Ascending
    ```

2. Чтобы упорядочить по фамилии, а затем по имени, добавьте в запрос оба поля:

    ```
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    Можно также указать `Descending` порядок от я до а.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-introduce-a-local-identifier"></a>Введение локального идентификатора

1. Добавьте код в этом разделе, чтобы ввести локальный идентификатор в выражение запроса. Локальный идентификатор будет содержать промежуточный результат. В следующем примере `name` — это идентификатор, содержащий объединение имени и фамилии учащегося. Локальный идентификатор можно использовать для удобства или повысить производительность, сохранив результаты выражения, которые в противном случае будут вычисляться несколько раз.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-project-one-field-in-the-select-clause"></a>Проецирование одного поля в предложении SELECT

1. Добавьте запрос и `For Each` цикл из этого раздела, чтобы создать запрос, который создает последовательность, элементы которой отличаются от элементов в источнике. В следующем примере источником является коллекция `Student` объектов, но возвращается только один элемент каждого объекта: имена учащихся, чье фамилия — Гарсиа. Так `currentStudent.First` как является строкой, тип данных последовательности, `studentQuery3` возвращаемой, — `IEnumerable(Of String)`это последовательность строк. Как и в предыдущих примерах, для определения типа данных для `studentQuery3` компилятора необходимо определить, используя вывод локального типа.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Наведите указатель `studentQuery3` мыши на код, чтобы убедиться, что назначенный тип имеет `IEnumerable(Of String)`значение.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Создание анонимного типа в предложении SELECT

1. Добавьте код из этого раздела, чтобы увидеть, как анонимные типы используются в запросах. Они используются в запросах, если требуется вернуть несколько полей из источника данных, а не полные записи (`currentStudent` записи в предыдущих примерах) или отдельные поля (`First` в предыдущем разделе). Вместо определения нового именованного типа, содержащего поля, которые необходимо включить в результат, необходимо указать поля в `Select` предложении, и компилятор создаст анонимный тип с этими полями в качестве свойств. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

    В следующем примере создается запрос, который возвращает имя и звание старших званий, чьи учебные заведения находятся в диапазоне от 1 до 10 в порядке академических званий. В этом примере тип `studentQuery4` должен быть определен, `Select` поскольку предложение возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="additional-examples"></a>Дополнительные примеры

Теперь, когда вы понимаете основы, ниже приведен список дополнительных примеров для демонстрации гибкости и возможностей [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов. Каждому примеру предшествует краткое описание того, что он делает. Наведите указатель мыши на переменную результата запроса для каждого запроса, чтобы увидеть выведенный тип. Для получения результатов используйте цикл.`For Each`

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Дополнительные сведения

После ознакомления с основными понятиями работы с запросами вы можете ознакомиться с документацией и примерами для конкретного типа [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] поставщика, который вас интересует:

- [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>См. также

- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Инициализаторы объектов: Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
