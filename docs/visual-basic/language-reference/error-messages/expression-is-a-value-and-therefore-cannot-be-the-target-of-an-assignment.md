---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826137"
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
  
 **Косвенный доступ.** Непрямой доступ через тип значения можно также создать эту ошибку. Рассмотрим следующий пример кода, который пытается установить значение <xref:System.Drawing.Point> обращения к ним косвенно через <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 Последней инструкцией в предыдущем примере завершается сбоем, так как она создает временное размещение для <xref:System.Drawing.Point> структура, возвращенная <xref:System.Windows.Forms.Control.Location%2A> свойство. Структура является типом значения, а временная структура не сохраняется после выполнения инструкции. Проблема решается путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, который создает постоянное выделение памяти для <xref:System.Drawing.Point> структуры. В следующем примере кода, которая может использоваться вместо последней инструкции в предыдущем примере.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Идентификатор ошибки:** BC30068  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если инструкция присваивает значение выражения, замените выражение одной записываемой переменной, свойства или элемента массива.  
  
-   Если инструкция делает косвенный доступ через тип значения (обычно структуры), создайте переменную для хранения типа значения.  
  
-   Присвойте переменной подходящей структурой (или другого типа значения).  
  
-   Используйте переменную для доступа к свойству, чтобы присвоить ему значение.  
  
## <a name="see-also"></a>См. также

- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
