---
title: "Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции | Microsoft Docs"
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
  - "bc30957"
  - "vbc30957"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30957"
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выполнение функции отменено из\-за истечения времени ожидания при выполнении предыдущей функции.Чтобы возобновить выполнение, сделайте еще один шаг или перезапустите отладку.  
  
 В отладчике Visual Studio выражение определило вызов процедуры, но другое вычисление превысило лимит времени.  
  
 Возможной причиной для возникновения у процедуры тайм\-аута является *бесконечный цикл*.  Для получения дополнительной информации см. [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 *Рекурсия* является особым случаем бесконечного цикла.  Для получения дополнительной информации см. [Рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Идентификатор ошибки:** BC30957  
  
### Чтобы исправить эту ошибку  
  
1.  Если возможно, определите, каким было вычисление предыдущей функции и причину превышения его времени ожидания.  В противном случае возможно повторное возникновение этой ошибки.  
  
2.  Либо сделайте следующий шаг в отладчике, либо завершите и перезапустите отладку.  
  
## См. также  
 [Отладка в Visual Studio](/visual-studio/debugger/debugging-in-visual-studio)   
 [Навигация по коду с помощью отладчика](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Выражения в Visual Basic](../Topic/Expressions%20in%20Visual%20Basic.md)