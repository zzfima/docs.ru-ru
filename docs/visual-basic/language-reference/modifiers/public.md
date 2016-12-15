---
title: "Public (Visual Basic) | Microsoft Docs"
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
  - "vb.Public"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Public - модификатор доступа"
  - "Public - ключевое слово"
  - "Public - ключевое слово, синтаксис"
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Public (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что один или несколько объявленных элементов программирования не имеют ограничений доступа.  
  
## Заметки  
 При публикации компонента или набора компонентов, например библиотеки классов, обычно требуется, чтобы элементы программирования были доступными для любого кода, поддерживаемого сборкой.  Чтобы предоставить такой неограниченный доступ к элементу, его можно объявить как `Public`.  
  
 Глобальный доступ является обычным уровнем доступа для элемента программирования, если не требуется ограничить к нему доступ.  Обратите внимание, что уровень доступа для элемента, объявленного внутри интерфейса, модуля, класса или структуры по умолчанию `Public`, если иное не объявляется отдельно.  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать `Public` только на уровне пространства имен, интерфейса или модуля.  Это означает, что контекст объявления для элемента `Public` должен быть исходным файлом, пространством имен, структурой, модулем, классом или интерфейсом и не может быть процедурой.  
  
## Поведение  
  
-   **Уровень доступа.** Весь код, который может получить доступ к модулю, классу или структуре, может получить доступ к его элементам `Public`.  
  
-   **Доступ по умолчанию.** Локальные переменные внутри процедуры по умолчанию имеют уровень доступа Public. Использовать любые другие модификаторы доступа для таких переменных нельзя.  
  
-   **Модификаторы доступа..** Ключевые слова, указывающие уровень доступа, называются *access modifiers*.  Для получения сведений о сравнении модификаторов доступа см. раздел [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Public` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)