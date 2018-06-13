---
title: Объявление переменной в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 6890ddfd8b463cd731ab3d8f39565b50a31a1192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656143"
---
# <a name="variable-declaration-in-visual-basic"></a>Объявление переменной в Visual Basic
Можно объявить переменную, чтобы указать ее имя и характеристики. Оператор объявления переменных — [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Его местоположение и содержание определяют характеристики переменной.  
  
 Правила именования переменных и рекомендации см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Уровни объявления  
  
### <a name="local-and-member-variables"></a>Локальные и переменные-члены  
 Объект *локальной переменной* —, объявленная внутри процедуры. Объект *переменной-члена* является членом типа Visual Basic; он объявлен на уровне модуля, внутри класса, структуры или модуля, но не внутри любых процедур для этого класса, структуры или модуля.  
  
### <a name="shared-and-instance-variables"></a>Экземпляров и общие переменные  
 В классе или структуре категория переменной-члена зависит от того, является ли он является общим. Если он объявляется с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) это ключевое слово, *общей переменной*, и существует в единственном экземпляре, общим для всех экземпляров класса или структуры.  
  
 В противном случае это *переменная экземпляра*, и отдельная копия создается для каждого экземпляра класса или структуры. Каждая копия переменной экземпляра доступна только для экземпляра класса или структуры, в котором он был создан. Она не зависит от копия переменной экземпляра в другой экземпляр этого класса или структуры.  
  
## <a name="declaring-data-type"></a>Объявление типа данных  
 [Как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение в операторе объявления можно задать тип данных или тип объекта объявление переменной. Можно указать любой из следующих типов для переменной:  
  
-   Простой тип данных, таких как `Boolean`, `Long`, или `Decimal`  
  
-   Составной тип данных, например, массив или структура.  
  
-   Тип объекта или класс, определенный в приложении или в другом приложении  
  
-   Объект [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] класса, такие как <xref:System.Windows.Forms.Label> или <xref:System.Windows.Forms.TextBox>  
  
-   Тип интерфейса, такие как <xref:System.IComparable> или <xref:System.IDisposable>  
  
 Можно объявить несколько переменных в одном операторе без повторения типа данных. В следующих инструкциях переменные `i`, `j`, и `k` объявлен как тип `Integer`, `l` и `m` как `Long`, и `x` и `y` как `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Дополнительные сведения о типах данных см. в разделе [типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Дополнительные сведения об объектах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [программирование с использованием компонентов](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Вывод локального типа  
 *Определение типа* используется для определения типов данных локальных переменных, объявленных без `As` предложения. Компилятор выводит тип переменной из типа выражения инициализации. Это позволяет объявлять переменные без явного указания типа. В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Если вы хотите использовать вывод локального типа `Option Infer` должно быть присвоено `On`. Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Характеристики объявленных переменных  
 *Время существования* переменной — это период времени, во время которого он доступен для использования. В общем случае переменная существует, пока продолжает существовать элемент, объявляющий ее (например, процедура или класс). Если переменная не требуется прекратиться после окончания времени существования содержащего ее элемента, никаких действий в объявлении необязательно. Если переменная должна существовать дольше, чем содержащий его элемент, можно включить `Static` или `Shared` ключевое слово в его `Dim` инструкции. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 *Область* переменной — это совокупность всех элементов кода, на него можно ссылаться без указания полного имени. Область переменной определяется которых она объявлена. Код, расположенный в заданной области можно использовать переменные, определенные в этом регионе без уточнения их имена. Дополнительные сведения см. в разделе [области в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Переменная *уровень доступа* представляет экстент коду, имеющему разрешение на доступ к нему. Это определяется модификатор доступа (такие как [открытый](../../../../visual-basic/language-reference/modifiers/public.md) или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md)), используемого в `Dim` инструкции. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Статические](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
