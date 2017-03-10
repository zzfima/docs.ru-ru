---
title: "Инициализаторы объектов: именованные и анонимные типы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ObjectInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "анонимные типы [Visual Basic], инициализаторы объектов"
  - "инициализаторы [Visual Basic]"
  - "свойства инициализации [Visual Basic]"
  - "именованные типы [Visual Basic]"
  - "инициализаторы объекта [Visual Basic]"
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Инициализаторы объектов: именованные и анонимные типы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Инициализаторы объектов позволяют задать свойства для сложных объектов с помощью одного выражения.  Они могут быть использованы для создания экземпляров именованных и анонимных типов.  
  
## Объявления  
 Объявления экземпляров именованных и анонимных типов могут выглядеть почти одинаково, но их результаты различны.  Каждая категория имеет возможности и ограничения.  В следующем примере показан удобный способ объявления и инициализации нового экземпляра именованного класса `Customer` с помощью списка инициализаторов объекта.  Обратите внимание, что имя класса указывается после ключевого слова `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_1.vb)]  
  
 Анонимный тип не имеет имени.  Таким образом, экземпляр анонимного типа не может содержать имя класса.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_2.vb)]  
  
 Требования и результаты двух объявлений различны.  Для `namedCust` класс `Customer` со свойством `Name` должен существовать, и объявление создает экземпляр этого класса.  Для `anonymousCust` компилятор определяет новый класс, имеющий одно строковое свойство с именем `Name`, и создает новый экземпляр этого класса.  
  
## Именованные типы  
 Инициализаторы объектов предоставляют простой способ вызова конструктора типа с последующим заданием значений для некоторых или всех свойств в одной инструкции.  Компилятор вызывает подходящий конструктор для оператора. Вызывается конструктор по умолчанию, если аргументы не представлены, или параметризованный конструктор, если передается один или несколько аргументов.  После этого указанные свойства инициализируются в том порядке, в котором они представлены в списке инициализаторов.  
  
 Каждая инициализация в списке инициализаторов состоит из назначения начального значения члену класса.  Имена и типы данных членов устанавливаются при определении класса.  В следующем примере класс `Customer` должен существовать и должен иметь элементы с именами `Name` и `City`, которые могут принимать строковые значения.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_3.vb)]  
  
 Тот же результат можно получить с помощью следующего кода:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_4.vb)]  
  
 Каждое из этих объявлений эквивалентно следующему примеру, в котором объект `Customer` создается с помощью конструктора по умолчанию и затем указываются начальные значения для свойств `Name` и `City` с помощью оператора `With`.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_5.vb)]  
  
 Если класс `Customer` содержит параметризованный конструктор, который позволяет отправлять значение, например параметра `Name`, то можно также объявить и инициализировать объект `Customer` следующими способами:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_6.vb)]  
  
 Нет необходимости инициализировать все свойства, как показано в следующем коде.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_7.vb)]  
  
 Однако список инициализации не может быть пустым.  Неинициализированные свойства сохраняют свои значения по умолчанию.  
  
### Вывод типа с именованными типами  
 Можно сократить код объявления `cust1`, скомбинировав инициализаторы объектов и вывод локального типа.  Это позволяет опустить условие `As` в объявлении переменной.  Тип данных переменной выводится из типа объекта, созданного при назначении.  В следующем примере типом `cust6` является `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_8.vb)]  
  
### Замечания об именованных типах  
  
-   Член класса не может быть инициализирован более одного раза в списке инициализаторов объекта.  Объявление `cust7` вызывает ошибку.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_9.vb)]  
  
-   Элемент можно использовать для инициализации самого себя или другого поля.  Если элемент используется до его инициализации, как в следующем объявлении `cust8`, то будет использовано значение по умолчанию.  Помните, что при обработке объявления, использующего инициализатор объекта, в первую очередь происходит вызов соответствующего конструктора.  После этого инициализируются отдельные поля в списке инициализаторов.  В следующих примерах параметру `Name` присваивается значение по умолчанию `cust8`, а инициализированное значение присваивается `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_10.vb)]  
  
     В следующем примере используется параметризованный конструктор `cust3` и `cust4` для объявления и инициализации `cust10` и `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_11.vb)]  
  
-   Инициализаторы объектов могут быть вложенными.  В следующем примере класс `AddressClass` имеет два свойства `City` и `State`, а класс `Customer` имеет свойство `Address`, которое является экземпляром класса `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_12.vb)]  
  
-   Список инициализации не может быть пустым.  
  
-   Инициализируемый экземпляр не может иметь тип Object.  
  
-   Инициализируемые члены класса не могут быть общими, только для чтения, константами или вызовами методов.  
  
-   Инициализируемые члены класса не могут быть индексированными или квалифицированными.  В следующих примерах возникают ошибки компилятора:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## Анонимные типы  
 Анонимные типы используют инициализаторы объектов для создания экземпляров новых типов, которые явно не определены и не именованы.  Вместо этого компилятор создает тип согласно свойствам, определенным в списке инициализаторов объекта.  Тип называется *анонимным типов*, поскольку его имя не указывается.  Например, сравните следующее объявление с более ранним для `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_13.vb)]  
  
 Единственное синтаксическое отличие состоит в том, что после `New` не указано имя типа данных.  Однако выполняемые действия сильно отличаются.  Компилятор определяет новый анонимный тип, который имеет два свойства \(`Name` и `City`\) и создает экземпляр этого типа с указанными значениями.  Вывод типа определяет типы `Name` и `City` \(в этом примере это строки\).  
  
> [!CAUTION]
>  Имя анонимного типа создается компилятором и имеет значение, которое может отличаться от созданного при предыдущей компиляции.  Код не должен использовать или полагаться на имя анонимного типа.  
  
 Так как имя типа недоступно, нельзя использовать условие `As` для объявления `cust13`.  Его тип должен быть выведен.  Если не использовать позднее связывание, использовать анонимные типы смогут только локальные переменные.  
  
 Анонимные типы обеспечивают важную поддержку запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Дополнительные сведения об использовании анонимных типов в запросах см. в разделах [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### Замечания об анонимных типах  
  
-   Как правило, все или большинство свойств в объявлении анонимного типа будут ключевыми свойствами, которые обозначаются с помощью кодового слова `Key` в начале имени свойства.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_14.vb)]  
  
     Дополнительные сведения о ключевых свойствах см. в разделе [Key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Подобно именованным типам в списке инициализаторов для определения анонимного типа должно быть объявлено хотя бы одно свойство.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_2.vb)]  
  
-   Когда экземпляр анонимного типа объявлен, компилятор создает соответствующее определение анонимного типа.  Имена и типы данных для свойств берутся из объявления экземпляра и включаются компилятором в определение.  Свойства не именуются и не определяются заранее, как это делалось для именованного типа.  Их типы выводятся.  Нельзя задать тип данных свойства с помощью условия `As`.  
  
-   Имена и значения свойств для анонимных типов могут быть установлены несколькими другими способами.  Например, свойство анонимного типа может принимать как имя и значение переменной, так и имя и значение свойства другого объекта.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_15.vb)]  
  
     Дополнительные сведения о параметрах определения свойств в анонимных типах см. раздел [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## См. также  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)   
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)