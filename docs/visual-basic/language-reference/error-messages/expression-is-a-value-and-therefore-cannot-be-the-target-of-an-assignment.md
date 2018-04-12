---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bec3e2d298160bd0b459dc3b7ef93b94648e439a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>Нельзя присвоить значение выражению, поскольку оно является значением
Оператор пытается присвоить значение выражению. Можно назначить значение только записываемой переменной, свойства или элемента массива во время выполнения. В следующем примере показано, как эта ошибка может возникать.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Аналогичные примеры можно применить к свойствам и элементам массива.  
  
 **Косвенный доступ.** Эту ошибку может также вызывать косвенный доступ через тип значения. Рассмотрим следующий пример кода, который пытается установить значение <xref:System.Drawing.Point> , обратившись к косвенно через <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 Последней инструкцией в предыдущем примере завершается ошибкой, так как она создает временный выделение для <xref:System.Drawing.Point> структуры, возвращенный <xref:System.Windows.Forms.Control.Location%2A> свойство. Структура является типом значения, а временная структура не сохраняется после выполнения инструкции. Проблемы путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, которая создает постоянное выделение памяти для <xref:System.Drawing.Point> структуры. В примере показан код, который можно заменить последней инструкции в предыдущем примере.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Идентификатор ошибки:** BC30068  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если инструкция присваивает значение выражения, замените выражение одной записываемой переменной, свойства или элемента массива.  
  
-   Если инструкция делает косвенный доступ через тип значения (обычно структуры), создайте переменную для хранения типа значения.  
  
-   Присвойте переменной подходящую структуру (или другого типа значения).  
  
-   Используйте переменную для доступа к свойству присвоено значение.  
  
## <a name="see-also"></a>См. также  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
