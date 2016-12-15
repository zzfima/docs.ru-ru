---
title: "Директивы (Visual Basic) | Microsoft Docs"
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
  - "директивы"
  - "директивы, компилятор Visual Basic"
  - "код Visual Basic, директивы"
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Директивы (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.  
  
## В этом подразделе  
 [Директива \#Const](../../../visual-basic/language-reference/directives/const-directive.md) — определение константы компилятора.  
  
 [Директива \#ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) — задание сопоставления между строками источника и текста, являющегося внешним по отношению к источнику.  
  
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) — компиляция выбранных блоков кода.  
  
 [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md) — сворачивание и скрытие частей кода в редакторе Visual Studio.  
  
 **\#Disable, \#Enable** — отключение и включение конкретных предупреждений для областей кода.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
  
```  
  
 Можно также отключить и включить список кодов предупреждений с разделителями\-запятыми.  
  
## Связанные подразделы  
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)