---
title: "Неявное преобразование делегата (Visual Basic) | Microsoft Docs"
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
  - "преобразования, неявный делегат"
  - "делегаты [Visual Basic], неявное преобразование"
  - "неявное преобразование делегата [Visual Basic]"
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Неявное преобразование делегата (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Гибкое преобразование в тип делегата позволяет присваивать делегатам или обработчикам подпрограммы и функции, даже когда их сигнатуры не идентичны. Таким образом, привязка к делегатам становится согласованной с привязкой, уже разрешенной для вызовов метода.  
  
## Параметры и тип возвращаемого значения  
 Вместо сопоставления точной сигнатуры ослабленное преобразование требует следующих условий при установке `Option Strict` в `On`:  
  
-   Должно существовать расширяющее преобразование типа данных каждого параметра делегата к типу данных соответствующего параметра назначенной функции или `Sub`.  В следующем примере делегат `Del1` имеет один параметр типа `Integer`.  Параметр `m` в назначенном лямбда\-выражении должен иметь тип данных для которых имеется расширяющее преобразование из `Integer`, например `Long` или `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Сужающие преобразования разрешены только в том случае, если `Option Strict` имеет значение `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Должно существовать расширяющее преобразование в обратном направлении из возвращаемого типа назначенной функции или `Sub` к возвращаемому типу делегата.  В следующих примерах, основная часть каждого назначенного лямбда\-выражения должно иметь значение типа данных, не большего по разрядности, чем `Integer`, так как возвращаемым типом `del1` является тип `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Если `Option Strict` имеет значение `Off`, расширяющее ограничение снимается в обоих направлениях.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## Пропуск параметра спецификации  
 Ослабленные делегаты также позволяют полностью опустить параметры спецификации в назначенном методе:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Обратите внимание, что не удается задать некоторые параметры и не указать другие.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 Возможность опустить параметры является полезной в ситуации, например при определении обработчика событий, где включены несколько сложных параметров.  Аргументы для некоторых обработчиков событий не используются.  Вместо этого обработчик непосредственно получает состояние элемента управления, к которому привязано событие, а аргументы игнорируются.  Ослабленные делегаты позволяют опустить аргументы в таких объявлениях, когда результат неоднозначен.  В следующем примере полностью заданный метод `OnClick` можно переписать как `RelaxedOnClick`.  
  
```vb#  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## Примеры AddressOf  
 Лямбда\-выражения используются в предыдущих примерах, чтобы облегчить наблюдение за связью между типами.  Однако ослабление разрешено для назначений делегата, которые используют `AddressOf`, `Handles` или `AddHandler`.  
  
 В следующем примере функции `f1`, `f2`, `f3` и `f4` могут быть назначены `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Следующей пример справедлив только в том случае, если `Option Strict` имеет значение `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## Игнорирование возвращаемого значения функции  
 Ослабленный делегат преобразования позволяет назначить функцию делегату `Sub`, при этом игнорируя значение, возвращаемое функцией.  Однако присвоить `Sub` делегату функции невозможно.  В следующем примере адрес функции `doubler` присваивается делегату `Sub` `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## См. также  
 [Лямбда\-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Практическое руководство. Передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)