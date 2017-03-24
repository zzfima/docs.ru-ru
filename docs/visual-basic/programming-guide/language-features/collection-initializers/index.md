---
title: "Инициализаторы коллекций (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CollectionInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "инициализаторы коллекций [Visual Basic]"
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Инициализаторы коллекций (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Инициализаторы набора* предоставляют сокращенный синтаксис, позволяющий создавать коллекцию и населять ее начальным набором значений.  Инициализаторы наборов полезны при создании коллекции из набора известных значений, например из списка команд меню или категорий, исходного набора числовых значений, статического списка строк, таких как названия дней или месяцев либо географических названий \(например, список штатов\), который используется для проверки.  
  
 Дополнительные сведения о коллекциях см. в разделе [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Инициализатор набора определяется по ключевому слову `From`, за которым следуют фигурные скобки \(`{}`\).  Это напоминает синтаксис литерала массива, описанный в разделе [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  Следующие примеры демонстрируют различные способы применения инициализаторов наборов для создания коллекций.  
  
 [!code-vb[VbVbalrCollectionInitializers#1](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  C\# также предоставляет инициализаторы наборов.  Инициализаторы наборов в C\# обеспечивают те же функциональные возможности, что и в Visual Basic.  Дополнительные сведения об инициализаторах наборов в C\# см. в разделе [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Синтаксис  
 Инициализатор набора состоит из списка разделенных запятыми и заключенных в фигурные скобки \(`{}`\) значений, которым предшествует ключевое слово `From`, как показано в следующем образце кода.  
  
 [!code-vb[VbVbalrCollectionInitializers#2](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_2.vb)]  
  
 При создании коллекции, например <xref:System.Collections.Generic.List%601> или <xref:System.Collections.Generic.Dictionary%602>, перед инициализатором набора необходимо указать тип коллекции, как показано в следующем образце кода.  
  
 [!code-vb[VbVbalrCollectionInitializers#13](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_3.vb)]  
  
> [!NOTE]
>  Для инициализации одного и того же объекта набора инициализатор набора и инициализатор объекта объединять нельзя.  Для инициализации объектов в инициализаторе набора можно использовать инициализаторы объектов.  
  
## Создание коллекции с помощью инициализатора набора  
 При создании коллекции с помощью инициализатора набора каждое значение, указанное в инициализаторе набора, передается надлежащему методу `Add` этой коллекции.  Например, при создании <xref:System.Collections.Generic.List%601> с помощью инициализатора набора каждое строковое значение в инициализаторе набора передается методу <xref:System.Collections.Generic.List%601.Add%2A>.  Если требуется создать коллекцию с помощью инициализатора набора, то следует указать допустимый тип коллекции.  Пример допустимых типов коллекций — классы, которые реализуют интерфейс <xref:System.Collections.Generic.IEnumerable%601> или наследуют от класса <xref:System.Collections.CollectionBase>.  Указанный тип должен также предоставлять метод `Add`, отвечающий следующим условиям:  
  
-   Метод `Add` должен быть доступен из области видимости, в которой вызывается инициализатор набора.  Если инициализатор набора применяется в сценарии, в котором можно обращаться к методам коллекции, не являющимся общими, то метод `Add` не должен обязательно быть открытым.  
  
-   Метод `Add` должен быть членом экземпляра или `Shared`\-членом класса коллекции либо же методом расширения.  
  
-   Метод `Add` должен сопоставляться на основе правил разрешения перегрузки с типами, предоставляемыми в инициализаторе набора.  
  
 В следующем примере кода показано, как создать коллекцию `List(Of Customer)` с помощью инициализатора набора.  При выполнении кода каждый объект `Customer` передается методу `Add(Customer)` универсального списка.  
  
 [!code-vb[VbVbalrCollectionInitializers#9](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_4.vb)]  
  
 В следующем примере кода показан эквивалентный код, в котором инициализатор набора не используется.  
  
 [!code-vb[VbVbalrCollectionInitializers#10](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_5.vb)]  
  
 Если метод `Add` коллекции имеет параметры, сопоставимые с конструктором объекта `Customer`, то значения параметров для метода `Add` можно вложить в инициализаторы наборов, как описывается в следующем разделе.  Если у коллекции такого метода `Add` не имеется, его можно создать как метод расширения.  Пример создания метода `Add` как метода расширения для коллекции см. в разделе [Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md).  Пример создания пользовательской коллекции, которая могла бы использоваться совместно с инициализатором набора, см. в разделе [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md).  
  
## Инициализаторы наборов с вложениями  
 В инициализатор набора можно вложить значения, чтобы указать конкретную перегрузку метода `Add` для создаваемой коллекции.  Значения, передаваемые методу `Add`, должны быть разделены запятыми и заключены в фигурные скобки \(`{}`\), как в литерале массива или инициализаторе набора.  
  
 При создании коллекции с помощью вложенных значений каждый элемент списка вложенных значений передается в качестве аргумента методу `Add`, соответствующему типу элемента.  В следующем примере кода создается коллекция <xref:System.Collections.Generic.Dictionary%602>, в которой ключи относятся к типу `Integer`, а значения — к типу `String`.  Каждый из списков вложенных значений сопоставляется с методом <xref:System.Collections.Generic.Dictionary%602.Add%2A> для `Dictionary`.  
  
 [!code-vb[VbVbalrCollectionInitializers#5](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_6.vb)]  
  
 Предыдущий пример кода эквивалентен следующему коду.  
  
 [!code-vb[VbVbalrCollectionInitializers#6](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/index_7.vb)]  
  
 Методу `Add` типа коллекции передаются только списки вложенных значений первого уровня вложения.  Более глубокие уровни вложения обрабатываются как литералы массива, а списки вложенных значений не сопоставляются с методом `Add` ни в одной из коллекций.  
  
## Связанные разделы  
  
|||  
|-|-|  
|Заголовок|Описание|  
|[Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Показывает, как создать метод расширения `Add` это можно использовать для заполнения коллекции значениями из инициализатора набора.|  
|[Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Показано, как включить использование инициализаторов набора, включив `Add` метод в классе, который реализует интерфейс коллекции  `IEnumerable`.|  
  
## См. также  
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Автоматически реализуемые свойства](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Практическое руководство. Инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)