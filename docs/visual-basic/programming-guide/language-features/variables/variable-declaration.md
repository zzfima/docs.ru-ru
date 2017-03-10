---
title: "Объявление переменной в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "переменные [Visual Basic], объявление"
  - "переменные-члены, объявления"
  - "оператор Dim, объявление переменных"
  - "объявление переменных"
  - "переменные [Visual Basic], область действия"
  - "переменные [Visual Basic], типы данных"
  - "типы данных [Visual Basic], объявления переменных"
  - "время жизни, переменные"
  - "переменные [Visual Basic], время жизни"
  - "уровни доступа, переменные"
  - "область действия, операторы объявления"
  - "переменные [Visual Basic], уровень доступа"
  - "локальные переменные, объявления"
  - "область действия, переменные"
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Объявление переменной в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Переменная объявляется для того, чтобы задать ее имя и характеристики.  Оператором объявления переменных является [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  Его местоположение и содержание определяют характеристики переменной.  
  
 Правила и соглашения по именованию переменных содержатся в [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Уровни объявления  
  
### Локальные переменные и переменные\-члены  
 *Локальная переменная* — это переменная, объявленная внутри процедуры.  *Переменная–член* является членом типа [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]; она объявляется на уровне модуля, внутри класса, структуры или модуля, но не внутри любых процедур этого класса, структуры или модуля.  
  
### Переменные экземпляров и общие переменные  
 В классе или структуре категория переменной–члена зависит от того, используется ли она совместно.  Если переменная объявлена с зарезервированным словом [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), она является *общей переменной* и существует в единственном экземпляре, разделяемом между всеми экземплярами класса или структуры.  
  
 В противном случае это *переменная экземпляра*, и отдельные ее копии создаются для каждого экземпляра класса или структуры.  Заданный копия переменной экземпляра доступно только на экземпляр класса или структуры, в котором он был создан.  Он не зависит от копии переменной экземпляра в любом другом экземпляре класса или структуры.  
  
## Объявление типа данных  
 Предложение [As](../../../../visual-basic/language-reference/statements/as-clause.md) в операторе объявления позволяет определить тип данных или тип объекта объявляемой переменной.  Можно указать любой из следующих типов переменных.  
  
-   Простой тип данных, например `Boolean`, `Long` или `Decimal`.  
  
-   Составной тип данных, например массив или структура.  
  
-   Объектный тип объекта или класс, определенный либо в вашем приложении, либо в другом  
  
-   Класс [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)], такой как <xref:System.Windows.Forms.Label> или <xref:System.Windows.Forms.TextBox>  
  
-   Тип интерфейса, такой как <xref:System.IComparable> или <xref:System.IDisposable>  
  
 Можно объявить несколько переменных в одном операторе без повторения типа данных.  В следующих операторах переменные `i` ,`j` и `k` объявляются как тип `Integer`, `l` и `m` как `Long`, `x` и `y` как `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Дополнительные сведения о типах данных содержатся в [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md).  Дополнительные сведения об объектах см. в разделах [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [Programming with Components](../Topic/Programming%20with%20Components.md).  
  
## Вывод локального типа  
 *Определение типа* используется для определения типов данных локальных переменных, объявленных без предложения `As`.  Компилятор выводит тип переменной из типа инициализированного выражения.  Показано, как объявлять переменные без явного указания типа.  В следующем примере и `num1`, и `num2` имеют тип целых чисел.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/variable-declaration_1.vb)]  
  
 Для использования вычисления локального типа `Option Infer` должно быть установлено в `On`.  Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Характеристик объявленных переменных  
 *Время жизни переменной* — это период времени, в течение которого переменную можно использовать.  В общем случае переменная существует, пока продолжает существовать элемент, объявляющий ее \(например, процедура или класс\).  Если существование переменной должно прекратиться после окончания времени существования содержащего его элемента, вам не нужно ничего делать специальное в объявлении.  Если переменная должна существовать дольше, чем содержащий ее элемент, можно включить ключевое слово `Static` или `Shared` в ее оператор `Dim`.  Дополнительные сведения см. в разделе [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 *Область действия* переменной — это совокупность всего кода, в котором можно обращаться к переменной без уточнения ее имени.  Область действия переменной определяется местом, в котором она была объявлена.  Код, расположенный в определенной области, может использовать переменную, объявленную в этой области, без уточнения ее имени.  Дополнительные сведения см. в разделе [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 *Уровень доступа* переменной — пространство кода, обладающего разрешением на доступ к ней.  Он определяется модификатором доступа \(например [Public](../../../../visual-basic/language-reference/modifiers/public.md) или [Private](../../../../visual-basic/language-reference/modifiers/private.md)\), который используется в инструкции `Dim`.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## См. также  
 [Практическое руководство. Создание новой переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md)