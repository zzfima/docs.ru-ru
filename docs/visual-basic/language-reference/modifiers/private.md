---
title: "Private (Visual Basic) | Microsoft Docs"
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
  - "vb.Private"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Private - ключевое слово"
  - "Private - ключевое слово, синтаксис"
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Private (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что один или несколько объявленных элементов программирования являются доступными только из их контекста объявления, в том числе и из любых вложенных типов.  
  
## Заметки  
 Если элемент программирования представляет особые возможности или содержит конфиденциальные данные, обычно требуется максимально ограничить доступ к нему.  Максимальное ограничение достигается, если доступ к элементу имеет только модуль, класс или определяющая его структура.  Чтобы ограничить доступ к элементу таким образом, можно объявить ее как `Private`.  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать зарезервированное слово `Private` только на уровне модуля.  Это означает, что контекст объявления для элемента `Private` должен быть модулем, классом или структурой и не может быть исходным файлом, пространством имен, интерфейсом или процедурой.  
  
## Поведение  
  
-   **Уровень доступа.** Весь код в контексте объявления может обращаться к его элементам `Private`.  Это относится к коду вложенного типа, такого как вложенный класс или выражение присваивания в перечислении.  Код вне контекста объявления не может обращаться к его элементам `Private`.  
  
-   **Модификаторы доступа..** Ключевые слова, указывающие уровень доступа, называются *access modifiers*.  Для получения сведений о сравнении модификаторов доступа см. раздел [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Модификатор `Private` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)