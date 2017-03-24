---
title: "Практическое руководство. Вызов Windows API (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "вызовы API"
  - "вызовы API, вызов неуправляемого кода"
  - "вызовы, хранимые процедуры"
  - "API Windows, вызов"
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Практическое руководство. Вызов Windows API (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В этом примере определяется и вызывается функция `MessageBox` в библиотеке user32.dll, после чего ей передается строка.  
  
## Пример  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на пространство имен <xref:System>.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Метод не статический, абстрактный, или же он был уже определен.  Родительский тип является типом интерфейса, или *name* или *dllName* имеет нулевую длину.  \(<xref:System.ArgumentException>\)  
  
-   *name* или *dllname* имеют значение `Nothing`.  \(<xref:System.ArgumentNullException>\)  
  
-   Содержащий тип был создан ранее с помощью метода `CreateType`.  \(<xref:System.InvalidOperationException>\)  
  
## См. также  
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ru-ru/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md)   
 [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)   
 [Defining a Method with Reflection Emit](http://msdn.microsoft.com/ru-ru/84fd3bf6-628f-41aa-83d9-b990cf926e81)   
 [Пошаговое руководство. Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)