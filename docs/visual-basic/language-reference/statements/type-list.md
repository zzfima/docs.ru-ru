---
title: "Список типов (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "StructureConstraint"
  - "vb.StructureConstraint"
  - "ClassConstraint"
  - "vb.ClassConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ограничение класса"
  - "ограничения, Class - ключевое слово"
  - "ограничения, параметры типа in"
  - "ограничения, Structure - ключевое слово"
  - "ограничения, универсальные типы в Visual Basic"
  - "универсальные параметры"
  - "универсальные шаблоны [Visual Basic], ограничения"
  - "универсальные шаблоны [Visual Basic], универсальные типы"
  - "универсальные шаблоны [Visual Basic], список типов"
  - "универсальные шаблоны [Visual Basic], параметры типа"
  - "параметры, универсальный"
  - "параметры, тип"
  - "ограничение структуры"
  - "параметры типа"
  - "параметры типа, ограничения"
  - "типы [Visual Basic], универсальный"
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Список типов (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает *параметры\-типы* для *стандартного* программного элемента  Несколько параметров разделяются запятыми.  Ниже представлен синтаксис для одного параметра\-типа.  
  
## Синтаксис  
  
```  
  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`genericmodifier`|Необязательный.  Может использоваться только в универсальных интерфейсах и делегатах.  Можно объявить ковариант типа с помощью ключевого слова [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) или контрвариант с помощью ключевого слова [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md).  Дополнительные сведения см. в разделе [Ковариация и контрвариация](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).|  
|`typename`|Обязательный.  Имя параметра\-типа.  Это заполнитель, заменяемый определенным типом, предоставляемым соответствующим аргументом типа.|  
|`constraintlist`|Необязательный.  Список требований, ограничивающих тип данных, который может быть задан для `typename`.  Если имеется несколько ограничений, заключайте их в фигурных скобках \(`{ }`\) и разделяйте их запятыми.  В начале списка ограничений необходимо указать ключевое слово [As](../../../visual-basic/language-reference/statements/as-clause.md).  `As` используется только один раз — в начале списка.|  
  
## Заметки  
 Каждый стандартный программный элемент должен получить хотя бы один параметр\-тип.  Параметр\-тип является заполнителем для определенного типа \(*построенного элемента*\), который задается в коде клиента при создании экземпляра стандартного типа.  Можно определить стандартный класс, структуру, интерфейс, процедуру или делегат.  
  
 Дополнительные сведения об определении стандартного типа содержатся в разделе [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  Дополнительные сведения об именах параметров\-типов см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Правила  
  
-   **Круглые скобки.** Предоставляемый список параметров\-типов необходимо заключить в круглые скобки, а список следует начать с ключевого слова[Of](../../../visual-basic/language-reference/statements/of-clause.md).  `Of` используется только один раз — в начале списка.  
  
-   **Ограничения.** Список *ограничений* для параметра\-типа может включать следующие элементы в любых сочетаниях.  
  
    -   Любое число интерфейсов.  Указанный тип должен реализовать каждый интерфейс в этом списке.  
  
    -   Не более одного класса.  Указанный тип должен наследоваться из этого класса.  
  
    -   Ключевое слово `New`.  Указанный тип должен предоставлять конструктор без параметров, к которому стандартный тип имеет доступ.  Это полезно, если параметр\-тип ограничивается с помощью одного или нескольких интерфейсов.  Тип, который реализует интерфейсы, необязательно должен предоставлять конструктор, и в зависимости от уровня доступа конструктора код стандартного типа может не иметь доступа к нему.  
  
    -   Любое из двух ключевых слов: `Class` или `Structure`.  Ключевое слово `Class` создает ограничение для параметра универсального типа, чтобы требовалось, чтобы любой передаваемый ему аргумент типа был ссылочным типом, например строкой, массивом делегатом или объектом, созданным из класса.  Ключевое слово `Structure` создает ограничение для параметра универсального типа, чтобы требовалось, чтобы любой передаваемый ему аргумент типа был типом значения, например структурой, перечислением или простейшим типом данных.  Нельзя включать вместе `Class` и `Structure` в одном и том же `constraintlist`.  
  
     Указанный тип должен удовлетворять каждому требованию из `constraintlist`.  
  
     Ограничения для каждого параметра\-типа не зависят от ограничений, наложенных на другие параметры\-типы.  
  
## Поведение  
  
-   **Подстановка времени компиляции.** При создании сформированного типа из стандартного программного элемента каждому параметру\-типу предоставляется определенный тип.  Компилятор Visual Basic подставляет данный предоставленный тип для каждого вхождения `typename` в стандартном элементе.  
  
-   **Отсутствие ограничений.** Если ограничения для параметра\-типа не указаны, код ограничивается операциями и членами, поддерживаемыми [Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md) для данного параметра\-типа.  
  
## Пример  
 Пример показывает каркас определения класса универсального словаря, включая каркас функции для добавления новой записи в словарь.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_1.vb)]  
  
## Пример  
 Поскольку `dictionary` является универсальным, код, использующий его, может создать различные объекты, каждый из которых будет иметь те же функциональные возможности, но выполняется для другого типа данных.  В следующем примере показана строка кода, которая создает объект `dictionary` с входными данными `String` и ключами `Integer`.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_2.vb)]  
  
## Пример  
 В следующем примере рассматривается каркас определения, созданный в предыдущем примере.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_3.vb)]  
  
## См. также  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Ковариация и контрвариация](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)