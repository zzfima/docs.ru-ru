---
title: "Написание запросов в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e870d5d0640c68fa57b07986f2bf8268fd5246c9
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Пошаговое руководство. Написание запросов в Visual Basic
В этом пошаговом руководстве демонстрируется использование возможностей языка Visual Basic для написания [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] выражений запросов. В примере демонстрируются способы создания запросов к списку объектов Student, как выполнение запросов и об их изменении. Запросы включают в себя несколько функций, в том числе инициализаторы объектов, вывод локального типа и анонимные типы.  
  
 После выполнения этого пошагового руководства, можно переходить к примерам и документации к конкретному [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] поставщика, которые вас интересуют. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]Поставщики включают [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="create-a-project"></a>Создание проекта  
  
#### <a name="to-create-a-console-application-project"></a>Создание проекта консольного приложения  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
3.  В **установленные шаблоны** выберите **Visual Basic**.  
  
4.  В списке типов проекта выберите **консольное приложение**. В **имя** введите имя для проекта и нажмите кнопку **ОК**.  
  
     Создать проект. По умолчанию он содержит ссылку на библиотеку System.Core.dll. Кроме того **импортированные пространства имен** списке [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) включает <xref:System.Linq?displayProperty=fullName>имен.</xref:System.Linq?displayProperty=fullName>  
  
5.  На [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), убедитесь, что **Option infer** равен **на**.  
  
## <a name="add-an-in-memory-data-source"></a>Добавить источник данных в памяти  
 Источник данных для запросов в этом руководстве приведен список `Student` объектов. Каждый `Student` объект содержит имя, фамилию, год и успеваемость студентов текста.  
  
#### <a name="to-add-the-data-source"></a>Чтобы добавить источник данных  
  
-   Определение `Student` класса и создайте список экземпляров класса.  
  
    > [!IMPORTANT]
    >  Код, необходимый для определения `Student` класса и создания списка, используемого в пошаговом руководстве приведены примеры [Практическое руководство: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Можно скопировать его оттуда и вставьте его в проект. Новый код заменяет код, появившийся при создании проекта.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Добавление нового учащегося в список учащихся  
  
-   Следуйте шаблону в `getStudents` метод, чтобы добавить еще один экземпляр `Student` класс к списку. Добавление студентов представит инициализаторы объектов. Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Создание запроса  
 При выполнении запроса, добавленного в этом разделе создает список студентов, успеваемость которых попадает в десятку. Поскольку запрос выбирает полную `Student` объект каждый раз тип результата запроса является `IEnumerable(Of Student)`. Однако тип запроса обычно не определен в определениях запроса. Вместо этого компилятор использует локальное определение типа для определения типа. Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Переменная диапазона запроса, `currentStudent`, служит в качестве ссылки на каждый `Student` экземпляра в источнике, `students`, предоставляя доступ к свойствам каждого объекта в `students`.  
  
#### <a name="to-create-a-simple-query"></a>Создание простого запроса  
  
1.  Найдите место в `Main` метод проекта, который помечен как показано ниже:  
  
     [!code-vb[VbLINQWalkthrough&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Скопируйте следующий код и вставьте его в.  
  
     [!code-vb[VbLINQWalkthrough&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Наведите указатель мыши на `studentQuery` в коде для проверки типа компилятора назначенных `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Выполнить запрос  
 Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса. Типичным механизмом выполнения запроса является `For Each` цикла. Каждому элементу в возвращаемой последовательности осуществляется с помощью переменной итерации цикла. Дополнительные сведения о выполнении запроса см. в разделе [Your первого запроса LINQ записи](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Чтобы выполнить запрос  
  
1.  Добавьте следующие `For Each` цикл под запросом в проекте.  
  
     [!code-vb[VbLINQWalkthrough&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Наведите указатель мыши на переменную цикла `studentRecord` для просмотра ее типа данных. Тип `studentRecord` определяется как `Student`, так как `studentQuery` возвращает коллекцию `Student` экземпляров.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
## <a name="modify-the-query"></a>Изменение запроса  
 Это упрощает просмотр результатов запроса, если они находятся в указанном порядке. Можно сортировать по любому доступному полю возвращаемую последовательность.  
  
#### <a name="to-order-the-results"></a>Для упорядочения результатов  
  
1.  Добавьте следующие `Order By` предложение между `Where` инструкции и `Select` инструкция запроса. `Order By` Предложение будет упорядочивать результаты в алфавитном порядке от А до Z, последней в соответствии с именем каждого студента.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Чтобы заказать по фамилии, а затем по имени, добавьте в запрос оба поля:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Можно также указать `Descending` Чтобы упорядочить от я до а.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-introduce-a-local-identifier"></a>Чтобы ввести локальный идентификатор  
  
1.  Добавьте код в этом разделе, чтобы ввести локальный идентификатор в выражение запроса. Локальный идентификатор будет содержать промежуточные результаты. В следующем примере `name` является идентификатором, который содержит объединение учащегося первого имени и фамилии. Локальный идентификатор может использоваться для удобства, или он может повысить производительность, сохраняя результаты выражения, в противном случае будет вычисляться несколько раз.  
  
     [!code-vb[VbLINQWalkthrough&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Проецирование одного поля в предложении Select  
  
1.  Добавьте запрос и `For Each` цикл из этого раздела, чтобы создать запрос, выводящий последовательность, элементы которой отличаются от элементов в исходной коллекции. В следующем примере источником является коллекция `Student` возвращаются объекты, но только один член каждого объекта: имена студентов, фамилия которых Орехов. Поскольку `currentStudent.First` является строкой, типом данных последовательности, возвращаемой `studentQuery3` — `IEnumerable(Of String)`, последовательность строк. Как и в предыдущих примерах, назначение данных введите `studentQuery3` остается компилятору определить с помощью локального определения типов.  
  
     [!code-vb[VbLINQWalkthrough&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Наведите указатель мыши на `studentQuery3` в коде, чтобы убедиться, что назначенный тип `IEnumerable(Of String)`.  
  
3.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Создание анонимного типа в предложении Select  
  
1.  Добавьте код из этого раздела, чтобы увидеть как анонимные типы используются в запросах. Они используются в запросах при необходимости возвращать несколько полей из источника данных вместо полных записей (`currentStudent` записей в предыдущих примерах) или одного поля (`First` в предыдущем разделе). Вместо определения нового именованного типа, содержащий поля, которые нужно включить в результат, можно указать поля в `Select` предложения и компилятор создает анонимный тип с этими полями в качестве его свойства. Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     В следующем примере создается запрос, возвращающий имя и успеваемость руководителями более высокого уровня, чья успеваемость находится между 1 и 10 в порядке успеваемости. В этом примере тип `studentQuery4` должен быть выведен, поскольку `Select` предложение возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.  
  
     [!code-vb[VbLINQWalkthrough №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Постройте и запустите приложение, нажав сочетание клавиш CTRL + F5. Обратите внимание на результаты в окне консоли.  
  
## <a name="additional-examples"></a>Дополнительные примеры  
 Теперь, когда вы знакомы с основами, ниже приведен список дополнительных примеров, который иллюстрирует гибкость и мощь [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов. Каждый пример предшествует краткое описание того, что он делает. Наведите указатель мыши на переменную результата запроса для каждого запроса, чтобы просмотреть определенный тип. Используйте `For Each` цикле для получения результатов.  
  
 [!code-vb[VbLINQWalkthrough&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Дополнительные сведения  
 После ознакомления с основными принципами работы с запросами, можно приступить к чтению документации и примеров для конкретного типа [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] поставщика интересующий вас:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)  
  
## <a name="see-also"></a>См. также  
 [Интегрированный в язык запрос (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Инициализаторы объектов: Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)
