---
title: "Friend (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Friend"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Friend - ключевое слово"
  - "Friend - модификатор доступа"
  - "ключевое слово Friend, синтаксис"
  - "сочетание ключевых слов Protected Friend"
  - "ключевое слово Friend, и Protected"
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Friend (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает на то, что один или несколько элементов доступны только из сборки, которая содержит их объявления.  
  
## Заметки  
 В большинстве случаев требуются элементы программирования, такие как классы и структуры, используемые всей сборкой, а не только компонентом, объявляющим их.  Однако может потребоваться не их быть доступны кода извне сборки \(например, если приложение собственническо\).  Если требуется ограничить доступ к элементу таким образом, можно объявить его с помощью модификатора `Friend`.  
  
 Код в других классах, структурах и модулях, которые компилируются к той же сборке, может иметь доступ ко всем элементам `Friend` в этой сборке.  
  
 метод доступа `Friend` часто оптимальный уровень программных элементов приложения и `Friend` уровень доступа по умолчанию интерфейса, модуля, класса или структуры.  
  
 `Friend` можно использовать только в модуле, интерфейса или уровне пространства имен.  Поэтому контекст объявления элемента `Friend` должен быть файл источника, пространства имен, интерфейса, модуль, класс или структура; не может быть процедурой.  
  
 Можно использовать модификатор `Friend` вместе с модификатором [Protected](../../../visual-basic/language-reference/modifiers/protected.md) в одном объявлении.  Это сочетание совещается оба метода доступа `Friend` и защищенный доступ на объявленных элементов, поэтому они доступны из любого места внутри одной и той же сборки, из своего класса и из производных классов.  Можно указать `Protected Friend` только для элементов классов.  
  
 Для сравнения `Friend` и других модификаторов доступа см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Можно указать, что другая сборка дружественной сборки, которая позволяет его, чтобы получить все типы и члены, которые помечены как `Friend`.  Для получения дополнительной информации см. [Дружественные сборки](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Пример  
 Следующий класс использует модификатор `Friend`, позволяющие другими элементами программирования в одной сборке получить доступ к определенным элементам.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/friend_1.vb)]  
  
## Использование  
 Модификатор `Friend` можно использовать в таких контекстах:  
  
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
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)