---
title: Написание запросов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6c5f7d288d805a6a25afa9a5b32a4550aaa76ec3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46480660"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Пошаговое руководство. Написание запросов в Visual Basic
В этом пошаговом руководстве показано, как можно использовать возможности языка Visual Basic для написания [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] выражений запросов. В примере демонстрируются способы создания запросов к списку объектов Student, как выполнять запросы и об их изменении. Запросы включают в себя несколько функций, включая инициализаторы объектов, вывод локального типа и анонимные типы.  
  
 После выполнения данного пошагового руководства, можно переходить на образцы кода и документации к конкретному [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] поставщика, которые вас интересуют. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Поставщики включают [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="create-a-project"></a>Создание проекта  
  
#### <a name="to-create-a-console-application-project"></a>Чтобы создать проект консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
3.  В **установленные шаблоны** выберите **Visual Basic**.  
  
4.  В списке типов проектов, щелкните **консольное приложение**. В **имя** введите имя для проекта и нажмите кнопку **ОК**.  
  
     Создается проект. По умолчанию он содержит ссылку на библиотеку System.Core.dll. Кроме того **импортированные пространства имен** списке [страница "ссылки", конструктор проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) включает в себя <xref:System.Linq?displayProperty=nameWithType> пространства имен.  
  
5.  На [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** присваивается **на**.  
  
## <a name="add-an-in-memory-data-source"></a>Добавить источник данных в памяти  
 Источник данных для запросов в этом пошаговом руководстве приведен список `Student` объектов. Каждый `Student` объект содержит имя, фамилию, год и успеваемость в тексте учащегося.  
  
#### <a name="to-add-the-data-source"></a>Добавление источника данных  
  
-   Определение `Student` класса и создания списка экземпляров класса.  
  
    > [!IMPORTANT]
    >  Код, необходимый для определения `Student` класса и создания списка, используемого в этом пошаговом руководстве примеры предоставляется в [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Можно скопировать его оттуда и вставьте его в проект. Новый код заменяет код, появившийся при создании проекта.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Чтобы добавить нового учащегося в список учащихся  
  
-   Шаблону `getStudents` метод, чтобы добавить другой экземпляр `Student` класс к списку. Добавление студентов вы узнаете о инициализаторы объектов. Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Создание запроса  
 При выполнении запроса, добавленного в этом разделе создает список студентов, успеваемость помещает их в первых десяти. Так как запрос выбирает полный `Student` объект каждый раз, а тип результата запроса является `IEnumerable(Of Student)`. Тем не менее тип запроса обычно не указан в определениях запроса. Вместо этого компилятор использует определение локального типа для определения типа. Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Переменная диапазона запроса, `currentStudent`, служащий в качестве ссылки на каждый `Student` экземпляр в источнике, `students`, предоставляя доступ к свойствам каждого объекта в `students`.  
  
#### <a name="to-create-a-simple-query"></a>Создание простого запроса  
  
1.  Найдите место в `Main` метод проекта, который помечен следующим образом:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Скопируйте следующий код и вставьте его в.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Наведите указатель мыши на `studentQuery` в код, чтобы убедитесь, что тип назначаемого компилятора `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Выполнить запрос  
 Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса. Типичным механизмом выполнения запроса является `For Each` цикла. Каждый элемент в возвращаемой последовательности осуществляется с помощью переменной итерации цикла. Дополнительные сведения о выполнении запросов см. в разделе [Your первого запроса LINQ записи](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Чтобы выполнить запрос  
  
1.  Добавьте следующий `For Each` цикл под запросом в проекте.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Наведите указатель мыши на управляющей переменной цикла `studentRecord` для просмотра типа данных. Тип `studentRecord` выводится как `Student`, так как `studentQuery` возвращает коллекцию `Student` экземпляров.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
## <a name="modify-the-query"></a>Изменение запроса  
 Это упрощает просмотр результатов запроса, если они находятся в указанном порядке. Можно отсортировать по любому доступному полю возвращаемую последовательность.  
  
#### <a name="to-order-the-results"></a>Упорядочение результатов  
  
1.  Добавьте следующий `Order By` предложение между `Where` инструкции и `Select` инструкции запроса. `Order By` Предложение будет упорядочивать результаты в алфавитном порядке от А до Z, используя фамилии учащихся.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Чтобы упорядочить по фамилии, а затем имя, добавьте оба поля в запрос:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Можно также указать `Descending` в порядке от Z до A.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-introduce-a-local-identifier"></a>Чтобы ввести локальный идентификатор  
  
1.  Добавьте код в этом разделе, чтобы ввести локальный идентификатор в выражении запроса. Локальный идентификатор будет содержать промежуточные результаты. В следующем примере `name` является идентификатором, который содержит объединение учащегося первый имени и фамилии. Для удобства можно использовать локальный идентификатор, или он может повысить производительность, сохраняя результаты выражения, в противном случае будет вычисляться несколько раз.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Проект с одним полем в предложении Select  
  
1.  Добавьте запрос и `For Each` цикл из этого раздела, чтобы создать запрос, который создает последовательность, элементы которой отличаются от элементов в исходной коллекции. В следующем примере источником является коллекция `Student` объекты, но только один элемент для каждого объекта, возвращается: имя, Фамилия студентов Орехов. Так как `currentStudent.First` представляет собой строку, тип данных последовательности, возвращаемой `studentQuery3` является `IEnumerable(Of String)`, последовательность строк. Как и в предыдущих примерах, тип назначения данных, для `studentQuery3` остается компилятору определить с помощью вывод локального типа.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Наведите указатель мыши на `studentQuery3` в коде, чтобы убедиться, что назначенный тип `IEnumerable(Of String)`.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Чтобы создать анонимный тип в предложении Select  
  
1.  Добавьте код из этого раздела, чтобы увидеть как анонимные типы используются в запросах. Использовать их в запросах, если вы хотите возвращать несколько полей из источника данных, а не все записи (`currentStudent` записей в предыдущих примерах) или отдельные поля (`First` в предыдущем разделе). Вместо определения нового именованного типа, содержащий поля, необходимо включить в результат, можно задавать поля в `Select` предложения и компилятор создает анонимный тип с этими полями в качестве его свойства. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     В следующем примере создается запрос, возвращающий имя и ранг руководителями, успеваемость составляет от 1 до 10, в порядке ранга для учебных заведений. В этом примере тип `studentQuery4` должен быть выведен, поскольку `Select` предложение возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
## <a name="additional-examples"></a>Дополнительные примеры  
 Теперь, когда вы знакомы с основами, ниже приведен список дополнительных примеров, который иллюстрирует гибкость и мощь [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов. Каждый пример предшествует краткое описание его назначение. Наведите указатель мыши над переменной результата запроса для каждого запроса, чтобы просмотреть определенный тип. Используйте `For Each` цикла для получения результатов.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Дополнительные сведения  
 После ознакомления с основными принципами работы с запросами, вы будете готовы прочитать документацию и примеры для конкретного типа [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] поставщика, которые вас интересуют:  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a>См. также

- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
