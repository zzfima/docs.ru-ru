---
title: "Partial (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Partial"
  - "partial"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "классы [Visual Basic]"
  - "классы [Visual Basic], разделяемые"
  - "Partial - ключевое слово [Visual Basic]"
  - "разделяемые, классы [Visual Basic]"
  - "разделяемые, структуры"
  - "разделяемые, типы [Visual Basic]"
  - "структуры, разделяемые"
  - "повышение типа"
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
caps.latest.revision: 36
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 36
---
# Partial (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что объявление типа — это частичное определение типа.  
  
 Вы можете разделить определение типа среди нескольких объявлений, используя ключевое слово `Partial`.  Можно использовать столько частичных объявлений, сколько необходимо, во множестве исходных файлах.  Однако все объявления должны находиться в одной сборке и одном пространстве имен.  
  
> [!NOTE]
>  Visual Basic поддерживает *разделяемые методы*, которые обычно реализуются в разделяемых классах.  Дополнительные сведения см. в разделах [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) и [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Синтаксис  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`attrlist`|Необязательно.  Список атрибутов, применяемых к этому событию.  [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки \(`< >`\).|  
|`accessmodifier`|Необязательно.  Указывает, какой код может получить доступ к этому событию.  См. раздел [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательно.  См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательно.  См. раздел [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательно.  См. раздел [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Обязательный.  Имя данного типа.  Оно должно соответствовать имени, определенному в других частичных объявлениях того же типа.|  
|`Of`|Необязательно.  Указывает, что это универсальный тип.  См. раздел [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Обязательный параметр, если используется параметр [Of](../../../visual-basic/language-reference/statements/of-clause.md).  См. раздел [Список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательно.  См. раздел [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Обязательный параметр, если используется параметр `Inherits`.  Имя класса или интерфейса, от которого наследует этот класс.|  
|`Implements`|Необязательно.  См. раздел [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Обязательный параметр, если используется параметр `Implements`.  Имена интерфейсов, реализуемых этим типом.|  
|`variabledeclarations`|Необязательно.  Операторы, которые объявляют дополнительные переменные и события для типа.|  
|`proceduredeclarations`|Необязательно.  Операторы, которые объявляют и определяют дополнительные процедуры для типа.|  
|`End Class` или `End Structure`|Завершает этот частичное определение `Class` или `Structure`.|  
  
## Заметки  
 Visual Basic использует разделяемые определения класса для разделения автоматически созданного кода и пользовательского кода в по отдельным файлам исходного кода.  Например, **конструктор форм Windows Forms** определяет разделяемые классы для элементов управления, таких как <xref:System.Windows.Forms.Form>.  Не следует изменять код, созданный в этих элементах управления.  
  
 Все правила для создания класса, структуры, интерфейса и модуля, например для использования модификатора и наследования, применяются при создании частичного типа.  
  
## Рекомендации  
  
-   В обычных условиях не следует разбивать один тип на два или более объявлений.  Поэтому в большинстве случаев ключевое `Partial` слово не требуется.  
  
-   Для удобочитаемости каждое частичное объявление типа должно включать ключевое слово `Partial`.  Компилятор позволяет пропускать ключевое слово только в одном частичном объявлении. Если это происходит в двух или более объявлениях, компилятор сообщает об ошибке.  
  
## Поведение  
  
-   **Объявления объединений.** Компилятор рассматривает тип как объединение всех его частичных объявлений.  Каждый модификатор из каждого частичного определения применяется ко всему типу, а каждый элемент из каждого частичного определения доступен для всего типа.  
  
-   **Повышение типа не допускается для частичных типов в модулях.** Если частичное определение находится внутри модуля, повышение типа этого типа автоматически отменяется.  В таком случае набор частичных определений может привести к непредсказуемым результатам и даже ошибкам компилятора.  Подробнее: [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Компилятор объединяет частичные определения, только если их полные пути идентичны.  
  
 Ключевое слово `Partial` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## Пример  
 Следующий пример разделяет определение класса `sampleClass` на два объявления, в каждом из которых определяется отдельная процедура `Sub`.  
  
 [!code-vb[VbVbalrKeywords#3](../../../visual-basic/language-reference/codesnippet/visualbasic/partial_1.vb)]  
  
 Два частичных определения в предыдущем примере могут находиться в одном или двух исходных файлах.  
  
## См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)