---
title: "Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic) | Microsoft Docs"
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
  - "Nothing - ключевое слово, назначение переменных"
  - "объектные переменные, пустая ссылка"
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Можно разорвать связь объектной переменной с любым экземпляром объекта, указав для нее значение [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### Чтобы разорвать связь объектной переменной с любым экземпляром объекта  
  
-   Задайте в операторе присваивания для переменной значение `Nothing`.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## Отказоустойчивость  
 Если код обращается к члену объектной переменной, которая была установлена в значение `Nothing`, то возникает исключение <xref:System.NullReferenceException>.  Если значение объектной переменной часто устанавливается в значение `Nothing` или переменная не инициализируется, то рекомендуется поместить операторы обращения к членам объекта в блок `Try...Catch...Finally`.  
  
## Безопасность платформы .NET Framework  
 Если объектная переменная используется для объектов, содержащих конфиденциальные или важные данные, то можно установить переменную в значение `Nothing` при отсутствии активного обращения к одному из этих объектов.  Это снижает вероятность получения доступа к данным для вредоносного кода.  
  
## См. также  
 <xref:System.NullReferenceException>   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Разрешение вопросов, связанных с исключениями: System.NullReferenceException](../Topic/Troubleshooting%20Exceptions:%20System.NullReferenceException.md)