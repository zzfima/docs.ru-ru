---
title: "Оператор IsTrue (Visual Basic) | Microsoft Docs"
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
  - "vb.istrue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsTrue - оператор"
  - "OrElse - оператор [Visual Basic]"
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор IsTrue (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет, является ли выражение `True`.  
  
 Нельзя вызывать `IsTrue` явно в коде, но компилятор Visual Basic может использовать это для создания кода из предложений `OrElse`.  Если определяется класс или структура, а затем используется переменная этого типа в предложении `OrElse`, необходимо определить `IsTrue` на этом классе или структуре.  
  
 Компилятор рассматривает операторы `IsTrue` и `IsFalse` как  *соответствующие пары* .  Это означает, что если определить один из них, необходимо также определить другой.  
  
## Использование IsTrue компилятором  
 После определения класса или структуры можно использовать переменную этого типа в предложениях `For`, `If`, `Else` `If`, или`While` или в условии `When`.  После этого компилятор потребует оператор, который преобразует тип в значение `Boolean`, чтобы проверить условие.  Он выполняет поиск подходящего оператора в следующем порядке:  
  
1.  Оператор расширяющего преобразования и класса или структуры для `Boolean`.  
  
2.  Оператор расширяющего преобразования и класса или структуры для `Boolean?`.  
  
3.  Оператор `IsTrue` Вашего класса или структуры.  
  
4.  Сужающее преобразование в `Boolean?`, которое не включает преобразование из `Boolean` в `Boolean?`.  
  
5.  Оператор сужающего преобразования в классе или структуре для `Boolean`.  
  
 Если не определены никакие преобразования в `Boolean` или оператор `IsTrue`, компилятор сообщает об ошибке.  
  
> [!NOTE]
>  Оператор `IsTrue` может быть  *перегруженным* , это означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере кода определяется контур структуры, содержащей определения для операторов `IsFalse` и `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## См. также  
 [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)