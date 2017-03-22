---
title: "Инициализаторы объектов: Именованные и анонимные типы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d684ad4f3dd47dc7400ea401a94660af832ef866
ms.lasthandoff: 03/13/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Инициализаторы объектов: именованные и анонимные типы (Visual Basic)
Инициализаторы объектов позволяют задать свойства для сложных объектов с помощью одного выражения. Они могут использоваться для создания экземпляров именованных и анонимных типов.  
  
## <a name="declarations"></a>Объявления  
 Объявления экземпляров именованных и анонимных типов могут выглядеть почти одинаково, но их результаты не совпадают. Каждая категория имеет возможности и ограничения собственных. В следующем примере показано удобный способ объявления и инициализации нового экземпляра именованного класса `Customer`, используя список инициализатора объекта. Обратите внимание, что имя класса указывается после ключевого слова `New`.  
  
 [!code-vb[VbVbalrObjectInit&#1;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Анонимный тип не имеет имени. Поэтому создание экземпляра анонимного типа не может содержать имя класса.  
  
 [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Требования и результаты двух объявлений не совпадают. Для `namedCust`, `Customer` класс, имеющий `Name` свойство должно уже существовать, и объявление создает экземпляр этого класса. Для `anonymousCust`, компилятор определяет новый класс, имеющий одно строковое свойство с именем `Name`и создает новый экземпляр этого класса.  
  
## <a name="named-types"></a>Именованные типы  
 Инициализаторы объектов предоставляют простой способ вызова конструктора типа, а затем задайте значения некоторых или всех свойств в одной инструкции. Компилятор вызывает подходящий конструктор для оператора: конструктор по умолчанию, если аргументы не указаны, или параметризованный конструктор, если отправляются один или несколько аргументов. После этого указанные свойства инициализируются в том порядке, в котором они перечислены в списке инициализаторов.  
  
 Каждая инициализация в списке инициализаторов состоит из назначения начального значения члену класса. При определении класса определяются имена и типы данных членов. В следующих примерах `Customer` класс должен существовать и должен иметь элементы с именами `Name` и `City` , которые могут принимать строковые значения.  
  
 [!code-vb[VbVbalrObjectInit&#3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Кроме того тот же результат можно получить с помощью следующего кода:  
  
 [!code-vb[VbVbalrObjectInit&#4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Каждое из этих объявлений эквивалентно в следующем примере, который создает `Customer` объекта с помощью конструктора по умолчанию, а затем задает начальные значения для `Name` и `City` свойств с помощью `With` инструкции.  
  
 [!code-vb[VbVbalrObjectInit&#5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Если `Customer` класс содержит параметризованный конструктор, который позволяет отправлять значение для `Name`, например, можно также объявить и инициализировать `Customer` объекта следующим образом:  
  
 [!code-vb[VbVbalrObjectInit №&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 Необходимо инициализировать все свойства, как показано в следующем коде.  
  
 [!code-vb[VbVbalrObjectInit&#7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Однако список инициализации не может быть пустым. Неинициализированные свойства сохраняют свои значения по умолчанию.  
  
### <a name="type-inference-with-named-types"></a>Вывод типа с именованными типами  
 Можно сократить код для объявления `cust1` путем объединения инициализаторы объектов и вывод локального типа. Это позволяет опускать `As` предложения в объявлении переменной. Тип данных переменной выводится из типа объекта, созданного при назначении. В следующем примере тип `cust6` — `Customer`.  
  
 [!code-vb[VbVbalrObjectInit №&8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Замечания об именованных типах  
  
-   Член класса не может инициализироваться более одного раза в списке инициализаторов объекта. Объявление `cust7` приводит к ошибке.  
  
     [!code-vb[VbVbalrObjectInit №&9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Элемент можно использовать для инициализации самого себя или другого поля. Если доступ к члену, прежде чем он был инициализирован, как показано в следующем объявлении `cust8`, будет использоваться значение по умолчанию. Помните, что при обработке объявления, использующего инициализатор объекта, первое, что происходит, вызывается соответствующий конструктор. После этого инициализируются отдельные поля в списке инициализаторов. В следующих примерах, значение по умолчанию для `Name` назначается для `cust8`, а инициализированное значение присваивается в `cust9`.  
  
     [!code-vb[VbVbalrObjectInit&#10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     В следующем примере используется параметризованный конструктор `cust3` и `cust4` в объявлении и инициализации `cust10` и `cust11`.  
  
     [!code-vb[VbVbalrObjectInit&11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Инициализаторы объектов могут быть вложенными. В следующем примере `AddressClass` — это класс, который имеет два свойства `City` и `State`и `Customer` класс имеет `Address` свойство, которое является экземпляром класса `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit&#12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Список инициализации не может быть пустым.  
  
-   Инициализируемый экземпляр не может иметь тип Object.  
  
-   Инициализируемые члены класса не может быть общие члены, только для чтения, константы или вызовы методов.  
  
-   Инициализируемые члены класса не удается индексировать или полное. В следующих примерах возникают ошибки компилятора:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Анонимные типы  
 Анонимные типы используют инициализаторы объектов для создания экземпляров новых типов, которые явно не определена и имя. Вместо этого компилятор создает тип согласно свойствам, определенным в списке инициализаторов объекта. Так как имя типа не указан, он называется *анонимного типа*. Например, сравните следующее объявление ранее одну `cust6`.  
  
 [!code-vb[VbVbalrObjectInit&#13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Синтаксически единственное отличие заключается в том, что имя не указано после `New` для типа данных. Однако что произойдет отличается. Компилятор определяет новый анонимный тип, который имеет два свойства `Name` и `City`и создает его экземпляр с указанными значениями. Вывод типа определяет типы `Name` и `City` в примере строки.  
  
> [!CAUTION]
>  Имя анонимного типа создается компилятором и может отличаться для разных компиляций. Код не должен использовать или полагаться на имя анонимного типа.  
  
 Так как имя типа недоступно, нельзя использовать `As` предложение для объявления `cust13`. Его тип должен быть выведен. Не использовать позднее связывание, это ограничивает использование анонимных типов локальными переменными.  
  
 Анонимные типы обеспечивают важную поддержку [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов. Дополнительные сведения об использовании анонимных типов в запросах см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [введения в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Замечания об анонимных типах  
  
-   Как правило, все или большинство свойств в объявлении анонимного типа будут ключевыми свойствами, которые обозначаются с помощью кодового слова `Key` перед именем свойства.  
  
     [!code-vb[VbVbalrObjectInit&#14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Дополнительные сведения о ключевых свойствах см. в разделе [ключ](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Подобно именованным типам в списке инициализаторов для определения анонимного типа необходимо объявить по крайней мере одно свойство.  
  
     [!code-vb[VbVbalrObjectInit&#2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   При объявлении экземпляра анонимного типа компилятор создает соответствующее определение анонимного типа. Имена и типы данных свойств берутся из объявления экземпляра и включаются компилятором в определение. Свойства не именуются и не определяются заранее, как было бы для именованного типа. Их типы выводятся. Нельзя задать тип данных свойства с помощью `As` предложения.  
  
-   Анонимные типы также можно задать имена и значения их свойств несколькими способами. Например свойство анонимного типа может принимать как имя и значение переменной, или имя и значение свойства другого объекта.  
  
     [!code-vb[VbVbalrObjectInit&#15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Дополнительные сведения о параметрах для определения свойств в анонимных типах см. в разделе [как: определить имена свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>См. также  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Практическое руководство: определить имена свойств и типы в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Ключ](../../../../visual-basic/language-reference/modifiers/key.md)   
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
