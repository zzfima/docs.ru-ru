---
title: "Объявление переменной в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8cabb2d319288653c80099c816e46e822429d6ec
ms.lasthandoff: 03/13/2017

---
# <a name="variable-declaration-in-visual-basic"></a>Объявление переменной в Visual Basic
Объявите переменную, чтобы указать ее имя и характеристики. Оператор объявления переменных — [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Его местоположение и содержание определяют характеристики переменной.  
  
 Правила именования переменных и рекомендации см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Уровни объявления  
  
### <a name="local-and-member-variables"></a>Локальные и переменные-члены  
 Объект *локальной переменной* —, объявленная внутри процедуры. Объект *переменной-члена* является членом [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] введите; он объявлен на уровне модуля, внутри класса, структуры или модуля, но не внутри любых процедур для этого класса, структуры или модуля.  
  
### <a name="shared-and-instance-variables"></a>Экземпляров и общие переменные  
 В классе или структуре категорию переменную-член зависит от того, является ли он является общим. Если он был объявлен с [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) это ключевое слово, *общей переменной*, и существует в единственном экземпляре, общим для всех экземпляров класса или структуры.  
  
 В противном случае это *переменную экземпляра*, и отдельные ее копии создаются для каждого экземпляра класса или структуры. Каждая копия переменной экземпляра доступна только для экземпляра класса или структуры, в котором он был создан. Он является независимым от копия переменной экземпляра в любом экземпляре класса или структуры.  
  
## <a name="declaring-data-type"></a>Объявление типа данных  
 [Как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение в операторе объявления позволяет определить тип данных или тип объекта объявление переменной. Можно указать любой из следующих типов переменных:  
  
-   Простой тип данных, таких как `Boolean`, `Long`, или`Decimal`  
  
-   Составные типы данных, такие как массив или структура.  
  
-   Тип объекта или класс, определенный в приложении или в другом приложении  
  
-   Объект [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] класса, такие как <xref:System.Windows.Forms.Label>или <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label>  
  
-   Тип интерфейса, такие как <xref:System.IComparable>или <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable>  
  
 Можно объявить несколько переменных в одном операторе без повторения типа данных. В следующих операторах переменные `i`, `j`, и `k` объявлен как тип `Integer`, `l` и `m` как `Long`, и `x` и `y` как `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Дополнительные сведения о типах данных см. в разделе [типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Дополнительные сведения об объектах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [программирование с использованием компонентов](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Вывод локального типа  
 *Вывод типа* используется для определения типов данных локальных переменных, объявленных без `As` предложения. Компилятор выводит тип переменной из типа выражения инициализации. Это позволяет объявлять переменные без явного указания типа. В следующем примере оба `num1` и `num2` являются строго типизированными как целые числа.  
  
 [!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Если вы хотите использовать вывод локального типа `Option Infer` должно быть присвоено `On`. Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Характеристики объявленных переменных  
 *Время существования* переменной — это период времени, во время которого он доступен для использования. В общем случае переменная существует, пока продолжает существовать элемент, объявляющий ее (например, процедура или класс). Если переменная не требуется прекратиться после окончания времени существования содержащего ее элемента, не требуется никаких действий в объявлении. Если переменная должна существовать дольше, чем содержащий ее элемент, можно включить `Static` или `Shared` ключевое слово в его `Dim` инструкции. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 *Область* переменной — это набор всех элементов кода, на него можно ссылаться без указания полного имени. Область переменной определяется, где она объявлена. Код, расположенный в заданном регионе можно использовать переменные, определенные в этой области, без уточнения их имена. Дополнительные сведения см. в разделе [область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Переменная *уровень доступа* является область кода, имеющего разрешение на доступ к нему. Это определяется модификатор доступа (такие как [открытый](../../../../visual-basic/language-reference/modifiers/public.md) или [закрытый](../../../../visual-basic/language-reference/modifiers/private.md)), используемого в `Dim` инструкции. Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Создание новой переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [Практическое руководство: перемещение данных в действие и из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Защищенные](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Статические](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
