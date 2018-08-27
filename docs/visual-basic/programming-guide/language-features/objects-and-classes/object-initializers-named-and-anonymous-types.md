---
title: 'Инициализаторы объектов: именованные и анонимные типы (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 612b1dcea0f776dfd4580803e76f2785e7d28da6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930594"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Инициализаторы объектов: именованные и анонимные типы (Visual Basic)
Инициализаторы объектов позволяют задавать свойства для сложного объекта с помощью одного выражения. Они могут использоваться для создания экземпляров именованных и анонимных типов.  
  
## <a name="declarations"></a>Объявления  
 Объявления экземпляров именованных и анонимных типов могут выглядеть почти одинаково, но их результаты не совпадают. Каждая категория имеет возможности и ограничения. В следующем примере показано удобный способ объявить и инициализировать экземпляр именованного класса `Customer`, с помощью списка инициализаторов объекта. Обратите внимание на то, что имя класса указывается после ключевого слова `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Анонимный тип не имеет имени. Поэтому создание экземпляра анонимного типа не может содержать имя класса.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Требования и результаты двух объявлений не совпадают. Для `namedCust`, `Customer` классом, имеющим `Name` должен существовать, и объявление создает экземпляр этого класса. Для `anonymousCust`, компилятор определяет новый класс, который имеет одно строковое свойство с именем `Name`и создает новый экземпляр этого класса.  
  
## <a name="named-types"></a>Именованные типы  
 Инициализаторы объектов предоставляют простой способ вызова конструктора типа, а затем задайте значения некоторых или всех свойств в одной инструкции. Компилятор вызывает соответствующий конструктор для инструкции: конструктор по умолчанию, если аргументы не указаны или параметризованный конструктор, если отправляются один или несколько аргументов. После этого указанные свойства инициализируются в порядке, в котором они перечислены в списке инициализаторов.  
  
 Каждая инициализация в списке инициализаторов состоит из назначения начального значения для члена класса. Имена и типы данных элементов определяются при определении класса. В следующих примерах `Customer` класс должен существовать и должен иметь элементы с именами `Name` и `City` , которые могут принимать строковые значения.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Кроме того можно получить тот же результат, используя следующий код:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Каждое из этих объявлений эквивалентно в следующем примере, который создает `Customer` объекта с помощью конструктора по умолчанию, а затем определяет начальные значения для `Name` и `City` свойств с помощью `With` инструкция.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Если `Customer` класс содержит параметризованный конструктор, который позволяет отправлять значение для `Name`, например, можно также объявить и инициализировать `Customer` объект одним из следующих способов:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 У вас нет для инициализации все свойства, как показано в следующем коде.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Однако список инициализации не может быть пустым. Неинициализированным свойствам сохраняют свои значения по умолчанию.  
  
### <a name="type-inference-with-named-types"></a>Определение типа с помощью именованных типов  
 Можно сократить код для объявления `cust1` путем объединения инициализаторы объектов и вывод локального типа. Это позволяет опускать `As` предложения в объявлении переменной. Тип данных переменной выводится из типа объекта, который создается путем назначения. В следующем примере тип `cust6` является `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Примечания о именованных типов  
  
-   Член класса не может инициализироваться более одного раза в списке инициализаторов объекта. Объявление `cust7` приводит к ошибке.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Член может использоваться для инициализации самого себя или другого поля. Если доступ к члену, прежде чем он был инициализирован, как показано в следующем объявлении `cust8`, будет использоваться значение по умолчанию. Помните, что при обработке объявление, которое использует инициализатора объекта, первое, что произойдет, что вызывается соответствующий конструктор. После этого инициализируются отдельные поля в списке инициализаторов. В следующих примерах, значение по умолчанию для `Name` назначается для `cust8`, и инициализированное значение назначается в `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     В следующем примере используется параметризованный конструктор `cust3` и `cust4` в объявлении и инициализации `cust10` и `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Инициализаторы объектов могут быть вложенными. В следующем примере `AddressClass` является классом, который имеет два свойства: `City` и `State`и `Customer` класс имеет `Address` свойство, которое является экземпляром класса `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Список инициализации не может быть пустым.  
  
-   Инициализируемый экземпляр не может иметь тип объекта.  
  
-   Инициализируемые члены класса не может быть общие члены, члены только для чтения, константы или вызовы методов.  
  
-   Не удается необходимо проиндексировать или указанием Инициализируемые члены класса. В следующих примерах возникают ошибки компилятора:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Анонимные типы  
 Анонимные типы использовать инициализаторы объектов для создания экземпляров новых типов, которые явно не определена и имя. Вместо этого компилятор создает тип в соответствии со свойствами, которую вы назначите в списке инициализаторов объекта. Так как имя типа не указан, он называется *анонимного типа*. Например, сравните следующее объявление с предыдущим для `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Единственное отличие синтаксически заключается в том, что имя не задано после `New` для типа данных. Однако что произойдет, несколько отличается. Компилятор определяет новый анонимный тип, который имеет два свойства: `Name` и `City`и создает его экземпляр с заданными значениями. Вывод типа определяет типы `Name` и `City` в примере строки.  
  
> [!CAUTION]
>  Имя анонимного типа создается компилятором и может отличаться для разных компиляций. Ваш код не следует использовать или полагаться на имя анонимного типа.  
  
 Поскольку имя типа не поддерживается, нельзя использовать `As` предложение для объявления `cust13`. Его тип должен быть определен. Не использовать позднее связывание, это ограничивает использование анонимных типов локальных переменных.  
  
 Анонимные типы обеспечивают критически важную поддержку для [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов. Дополнительные сведения об использовании анонимных типов в запросах см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Замечания об анонимных типах  
  
-   Как правило, все или большинство свойств в объявлении анонимного типа будут ключевыми свойствами, которые обозначаются введите ключевое слово `Key` перед именем свойства.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Дополнительные сведения о свойствах см. в разделе [ключ](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Как и под названием типы списков инициализаторов, для определения анонимного типа необходимо объявить по крайней мере одно свойство.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   При объявлении экземпляра анонимного типа, компилятор создает соответствующее определение анонимного типа. Имена и типы данных свойств берутся из объявления экземпляра и включаются компилятором в определении. Свойства не являются с именем и определять заранее, как было бы для именованного типа. Выводятся их типы. Типы данных свойств нельзя задать с помощью `As` предложение.  
  
-   Анонимные типы также можно установить имена и значения их свойств несколькими способами. Например свойство анонимного типа может занять имя и значение переменной, или имя и значение свойства другого объекта.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Дополнительные сведения о параметрах для определения свойств в анонимных типах см. в разделе [как: определить имена свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>См. также  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)  
 [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
