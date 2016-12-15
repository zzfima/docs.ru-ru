---
title: "Контексты объявления и уровни доступа по умолчанию (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "уровни доступа, уровни по умолчанию"
  - "уровни доступа, Visual Basic"
  - "Контексты объявления, Visual Basic"
  - "уровень модуля, определенный"
  - "Уровень пространства имен, определенный"
  - "уровень процедуры, определенный"
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Контексты объявления и уровни доступа по умолчанию (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом подразделе описано, какие типы Visual Basic могут быть объявлены внутри других типов, и каковы их уровни доступа по умолчанию, если не указано иное.  
  
## Уровни контекста объявления  
 *Контекстом объявления* элемента программирования является область кода, в которой он был объявлен.  Чаще всего, это другой программный элемент, который затем называется *содержащим элементом*.  
  
 Существуют следующие уровни для контекстов объявления:  
  
-   *Уровень пространства имен* — в исходном файле или в пространстве имен, но не в классе, структуре, модуле или интерфейсе.  
  
-   *Уровень модуля* — внутри класса, структуры, модуля или интерфейса, но не в процедуре или блоке.  
  
-   *Уровень процедуры* — внутри процедуры или блока \(например, `If` или `For`\).  
  
 В следующей таблице показаны уровни доступа по умолчанию для различных элементов программирования, в зависимости от их контекстов объявления.  
  
|Объявленный элемент|Уровень пространства имен|Уровень модуля|Уровень процедуры|  
|-------------------------|-------------------------------|--------------------|-----------------------|  
|Переменная \([Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)\)|Недопустимо|`Private` \(`Public` в `Structure`, недопустимо в `Interface`\)|`Public`|  
|Константа \([Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)\)|Недопустимо|`Private` \(`Public` в `Structure`, недопустимо в `Interface`\)|`Public`|  
|Перечисление \([Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)\)|`Friend`|`Public`|Недопустимо|  
|Класс \([Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)\)|`Friend`|`Public`|Недопустимо|  
|Структура \([Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)\)|`Friend`|`Public`|Недопустимо|  
|Модуль \([Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)\)|`Friend`|Недопустимо|Недопустимо|  
|Интерфейс \([Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)\)|`Friend`|`Public`|Недопустимо|  
|Процедура \([Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md), [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)\)|Недопустимо|`Public`|Недопустимо|  
|Внешняя ссылка \([Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)\)|Недопустимо|`Public` \(недопустимо в `Interface`\)|Недопустимо|  
|Оператор \([Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)\)|Недопустимо|`Public` \(недопустимо в `Interface` или `Module`\)|Недопустимо|  
|Свойство \([Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)\)|Недопустимо|`Public`|Недопустимо|  
|Свойство по умолчанию \([Default](../../../visual-basic/language-reference/modifiers/default.md)\)|Недопустимо|`Public` \(недопустимо в `Module`\)|Недопустимо|  
|Событие \([Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)\)|Недопустимо|`Public`|Недопустимо|  
|Делегат \([Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)\)|`Friend`|`Public`|Недопустимо|  
  
 Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## См. также  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)