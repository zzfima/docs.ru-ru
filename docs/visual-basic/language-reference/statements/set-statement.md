---
title: "Инструкция Set (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Set"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "свойства [Visual Basic], только запись"
  - "процедуры свойств, Set - операторы"
  - "Set - оператор"
  - "Set - оператор, синтаксис"
  - "свойства только для записи"
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Инструкция Set (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет свойство `Set`, которое используется для присваивания свойству значения.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## Части  
 `attributelist`  
 Необязательный.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязателен максимум для одного из операторов `Get` и `Set` в этом свойстве.  Может принимать следующие значения:  
  
-   [Защищенный](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Обязательный.  Параметр, содержащий новое значение свойства.  
  
 `datatype`  
 Требуется, если для `Option Strict` установлено значение `On`.  Тип данных параметра `value`.  Указанный тип данных должен совпадать с типом данных свойства, для которого объявляется данный оператор `Set`.  
  
 `statements`  
 Необязательный.  Один или несколько операторов, которые выполняются при вызове процедуры свойства `Set`.  
  
 `End Set`  
 Обязательный.  Завершает определение процедуры свойства `Set`.  
  
## Заметки  
 Каждое свойство должно иметь процедуру свойства `Set`, если только свойство не помечено как `ReadOnly`.  Процедура `Set` используется для присвоения значения свойства.  
  
 Visual Basic автоматически вызывает процедуру свойства `Set`, когда оператор присваивания предоставляет значение, хранимое в свойстве.  
  
 Visual Basic передает параметр в процедуру `Set` во время назначения свойств.  Если параметры для блока `Set` не предоставляются пользователем, интегрированная среда разработки \(IDE\) использует неявный параметр с именем `value`.  Параметр содержит значение, присваиваемое свойству.  Обычно это значение хранится в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.  
  
 Основная часть объявления свойства может содержать только процедуры `Get` и `Set` свойства между оператором [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property`.  Оно не может хранить что\-либо кроме этих процедур.  В частности, оно не может хранить текущее значение свойства.  Это значение следует хранить за пределами свойства, так как если хранить его внутри любой из процедур свойства, другая процедура свойства не сможет получить к нему доступ.  Обычным подходом является хранение значения в переменной [Private](../../../visual-basic/language-reference/modifiers/private.md), объявленной на том же уровне, что и свойство.  Процедуру `Set` необходимо определить внутри свойства, к которому оно применимо.  
  
 Процедура `Set` имеет уровень доступа к свойству, в котором содержится, по умолчанию, если не используется инструкция `accessmodifier` в операторе `Set`.  
  
## Правила  
  
-   **Смешанные уровни доступа.** При определении свойства для чтения и записи можно указать другой уровень доступа для процедур `Get` или `Set`, но не для обеих.  При этом уровень доступа процедуры должен быть более строгими, чем уровень доступа свойства.  Например, если свойство объявлено `Friend`, можно объявить процедуру `Set` как `Private`, но не `Public`.  
  
     При определении свойства `WriteOnly`, процедура `Set` представляет все свойство.  Нельзя объявлять другой уровень доступа для `Set`, поскольку таким образом устанавливается два уровня доступа для свойства.  
  
## Поведение  
  
-   **Возвращение из процедуры свойства.** Когда процедура`Set` возвращается к коду вызова, выполнение продолжается после инструкции, которая предоставляет значение для хранения.  
  
     Процедуры свойства `Set` могут возвращаться с помощью либо [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md), либо [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства.  Любое количество операторов `Exit Property` и `Return` может использоваться в любом месте процедуры, и их также можно использовать вместе с операторами `Exit Property` и `Return`.  
  
## Пример  
 В следующем примере используется инструкция `Set` для задания значения свойства.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## См. также  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)