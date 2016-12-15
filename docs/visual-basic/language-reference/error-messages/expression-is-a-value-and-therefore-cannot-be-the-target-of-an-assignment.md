---
title: "Нельзя присвоить значение выражению, поскольку оно является значением | Microsoft Docs"
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
  - "bc30068"
  - "vbc30068"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30068"
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Нельзя присвоить значение выражению, поскольку оно является значением
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Инструкция пытается присвоить значение выражению.  Можно назначить значение только записываемой переменной, свойству или элементу массива во время выполнения.  В следующем примере показано, как эта ошибка может возникать.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Аналогичные примеры можно применить к свойствам и элементам массива.  
  
 **Косвенный доступ.** Эта ошибка может быть также вызвана косвенным доступом через тип "значение".  Рассмотрим следующий пример кода, который пытается установить значение <xref:System.Drawing.Point> путем доступа к нему косвенно через <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 Последняя инструкция из предыдущего примера завершается сбоем, так как она создает только временное выделение памяти для структуры <xref:System.Drawing.Point>, возвращенной свойством <xref:System.Windows.Forms.Control.Location%2A>.  Структура является типом "значение", а временная структура не сохраняется после выполнения инструкции.  Проблема решается путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, которая создает постоянное выделение памяти для структуры <xref:System.Drawing.Point>.  В следующем примере показан код, которым можно заменить последнюю инструкцию из предыдущего примера.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Идентификатор ошибки**: BC30068  
  
### Чтобы исправить эту ошибку  
  
-   Если оператор присваивает значение выражению, то замените выражение простой записываемой переменной, свойством или элементом массива.  
  
-   Если инструкция делает косвенный доступ через тип "значение" \(обычно структуры\), то создайте переменную для хранения типа "значение".  
  
-   Присвойте переменной подходящую структуру \(или другой тип "значение"\).  
  
-   Используйте переменную для доступа к свойству для присвоения ей значения.  
  
## См. также  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Устранение неполадок в процедурах](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)