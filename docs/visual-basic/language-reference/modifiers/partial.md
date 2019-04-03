---
title: Partial (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: 0f74935d58d47e65b5eb614abc86a3fc9c8e6c42
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838369"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)
Указывает, что объявление типа — это частичное определение типа.  
  
 Вы можете разделить определение типа среди нескольких объявлений, используя ключевое слово `Partial`. Можно использовать столько частичных объявлений, сколько необходимо, во множестве исходных файлах. Однако все объявления должны находиться в одной сборке и одном пространстве имен.  
  
> [!NOTE]
>  Visual Basic поддерживает *разделяемые методы*, которые обычно реализуются в разделяемых классах. Дополнительные сведения см. в разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) и [оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attrlist`|Необязательный параметр. Список атрибутов, применяемых к этому событию. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловых скобках (`< >`).|  
|`accessmodifier`|Необязательный параметр. Указывает, какой код может получить доступ к этому событию. См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный параметр. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательный параметр. См. в разделе [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный параметр. См. в разделе [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Обязательный. Имя данного типа. Оно должно соответствовать имени, определенному в других частичных объявлениях того же типа.|  
|`Of`|Необязательный параметр. Указывает, что это универсальный тип. См. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Требуется при использовании [из](../../../visual-basic/language-reference/statements/of-clause.md). См. в разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный параметр. См. в разделе [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Обязательный параметр, если используется параметр `Inherits`. Имя класса или интерфейса, от которого наследует этот класс.|  
|`Implements`|Необязательный параметр. См. в разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Обязательный параметр, если используется параметр `Implements`. Имена интерфейсов, реализуемых этим типом.|  
|`variabledeclarations`|Необязательный параметр. Операторы, которые объявляют дополнительные переменные и события для типа.|  
|`proceduredeclarations`|Необязательный параметр. Операторы, которые объявляют и определяют дополнительные процедуры для типа.|  
|`End Class` или `End Structure`|Завершает этот частичное определение `Class` или `Structure`.|  
  
## <a name="remarks"></a>Примечания  
 Visual Basic использует разделяемые определения класса для разделения автоматически созданного кода и пользовательского кода в по отдельным файлам исходного кода. Например, **конструктор форм Windows Forms** определяет разделяемые классы для элементов управления, таких как <xref:System.Windows.Forms.Form>. Не следует изменять код, созданный в этих элементах управления.  
  
 Все правила для создания класса, структуры, интерфейса и модуля, например для использования модификатора и наследования, применяются при создании частичного типа.  
  
## <a name="best-practices"></a>Рекомендации  
  
-   В обычных условиях не следует разбивать один тип на два или более объявлений. Поэтому в большинстве случаев ключевое `Partial` слово не требуется.  
  
-   Для удобочитаемости каждое частичное объявление типа должно включать ключевое слово `Partial`. Компилятор позволяет пропускать ключевое слово только в одном частичном объявлении. Если это происходит в двух или более объявлениях, компилятор сообщает об ошибке.  
  
## <a name="behavior"></a>Поведение  
  
-   **Объявления объединений.** Компилятор рассматривает тип как объединение всех его частичных объявлений. Каждый модификатор из каждого частичного определения применяется ко всему типу, а каждый элемент из каждого частичного определения доступен для всего типа.  
  
-   **Повышение типа не допускается для частичных типов в модулях.** Если частичное определение находится внутри модуля, повышение типа этого типа автоматически отменяется. В таком случае набор частичных определений может привести к непредсказуемым результатам и даже ошибкам компилятора. Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Компилятор объединяет частичные определения, только если их полные пути идентичны.  
  
 Ключевое слово `Partial` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a>Пример  
 Следующий пример разделяет определение класса `sampleClass` на два объявления, в каждом из которых определяется отдельная процедура `Sub`.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Два частичных определения в предыдущем примере могут находиться в одном или двух исходных файлах.  
  
## <a name="see-also"></a>См. также

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
