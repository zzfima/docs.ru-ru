---
title: "Оператор Get | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Get"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Get - ключевое слово"
  - "Get - оператор"
  - "Get - оператор, синтаксис"
  - "свойства [Visual Basic], только для чтения"
  - "процедуры свойств, Get - операторы"
  - "свойства только для чтения"
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Get
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет процедуру свойства `Get`, которая используется для извлечения значения свойства.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`attributelist`|Необязательный.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязателен максимум для одного из операторов `Get` и `Set` в этом свойстве.  Может принимать следующие значения:<br /><br /> -   [Защищенный](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Необязательный.  Один или несколько операторов, которые выполняются при вызове процедуры свойства `Get`.|  
|`End Get`|Обязательный.  Завершает определение процедуры свойства `Get`.|  
  
## Заметки  
 Каждое свойство должно иметь `Get` процедуру свойства, если только свойство не помечено как `WriteOnly`.  Процедура `Get` используется для возвращения текущего значения свойства.  
  
 Visual Basic автоматически вызывает процедуру свойства `Get`, когда выражение запрашивает значение свойства.  
  
 Основная часть объявления свойства может содержать только процедуры `Get` и `Set` свойства между оператором [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property`.  Оно не может хранить что\-либо кроме этих процедур.  В частности, оно не может хранить текущее значение свойства.  Это значение следует хранить за пределами свойства, так как если хранить его внутри любой из процедур свойства, другая процедура свойства не сможет получить к нему доступ.  Обычным подходом является хранение значения в переменной [Private](../../../visual-basic/language-reference/modifiers/private.md), объявленной на том же уровне, что и свойство.  Процедуру `Get` необходимо определить внутри свойства, к которому оно применимо.  
  
 Процедура `Get` имеет уровень доступа к свойству, в котором содержится, по умолчанию, если не используется инструкция `accessmodifier` в операторе `Get`.  
  
## Правила  
  
-   **Смешанные уровни доступа.** При определении свойства для чтения и записи можно указать другой уровень доступа для процедур `Get` или `Set`, но не для обеих.  При этом уровень доступа процедуры должен быть более строгими, чем уровень доступа свойства.  Например, если свойство объявлено `Friend`, можно объявить процедуру `Get` как `Private`, но не `Public`.  
  
     При определении свойства `ReadOnly`, процедура `Get` представляет все свойство.  Нельзя объявлять другой уровень доступа для `Get`, поскольку, будет установлено два уровня доступа для свойства.  
  
-   **Возвращаемый тип.** При помощи [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) можно объявлять тип данных возвращаемого значения.  Процедура `Get` автоматически возвращает этот тип данных.  Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если в операторе `Property` не указан `returntype`, процедура возвращает `Object`.  
  
## Поведение  
  
-   **Возвращение из процедуры.** Когда процедура `Get` возвращается в код вызова, выполнение продолжается в операторе, запросившем значение свойства.  
  
     Процедуры свойства `Get` могут возвращать значение, используя либо [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md), или присваивая возвращаемое значение имени свойства.  Дополнительные сведения см. в разделе "Возвращаемое значение" [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства.  Любое количество операторов `Exit Property` и `Return` может использоваться в любом месте процедуры, и их также можно использовать вместе с операторами `Exit Property` и `Return`.  
  
-   **Возвращаемое значение.** Для возвращения значения из процедуры `Get` можно присвоить значение имени свойства или включить его в [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  Оператор `Return` одновременно назначает возвращаемое значение `Get` и выходит из процедуры.  
  
     При использовании `Exit Property` без присвоения значения имени свойства, процедура `Get` возвращает значение типа данных свойства по умолчанию.  Дополнительные сведения см. в разделе "Возвращаемое значение" [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     В следующем примере показано два способа возвращения значения для свойства `quoteForTheDay`, доступного только для чтения, значение содержится в частной переменной `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## Пример  
 В следующем примере используется оператор `Get` для возвращения значения свойства.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## См. также  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Пошаговое руководство. Определение классов](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)