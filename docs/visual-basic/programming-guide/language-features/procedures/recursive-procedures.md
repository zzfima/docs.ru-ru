---
title: "Рекурсивные процедуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "функции [Visual Basic], рекурсивный вызов"
  - "процедуры, вызов"
  - "процедуры, рекурсивные"
  - "процедуры, которые вызывают сами"
  - "рекурсия"
  - "рекурсивные процедуры"
  - "код Visual Basic, процедуры"
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Рекурсивные процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Рекурсивная процедура* — это процедура, которая вызывает сама себя.  Как правило, это не самый эффективный способ написания кода [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Приведенная ниже процедура использует рекурсию для вычисления факториала исходного аргумента:  
  
 [!code-vb[VbVbcnProcedures#51](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## Рассмотрение рекурсивных процедур  
 **Ограничивающие условия**.  Необходимо разработать рекурсивную процедуру для проверки по крайней мере одного условия, которое может прервать рекурсию, а также необходимо рассмотреть случаи, когда такое условие не выполняется в течение разумного числа рекурсивных вызовов.  Без, по крайней мере, одного условия, которое может быть выполнено без ошибок, возникает большой риск выполнения в бесконечном цикле.  
  
 **Использование памяти**.  Приложение имеет ограниченный объем пространства для локальных переменных.  Каждый раз, когда процедура вызывает саму себя, она использует больше этого пространства для дополнительных копий ее локальных переменных.  Если этот процесс будет продолжаться неопределенно долго, он в конечном счете вызовет ошибку <xref:System.StackOverflowException>.  
  
 **Эффективность**.  Почти всегда можно заменить цикл для рекурсии.  Цикл не имеет дополнительных издержек аргументов передачи, инициализации дополнительного хранилища и возврат значений.  Производительность может быть гораздо выше без рекурсивного вызова.  
  
 **Взаимная рекурсия**.  Можно наблюдать очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга.  Такой макет представляет те же проблемы, что и одна рекурсивная процедура, но это может быть сложнее обнаружить и отладить.  
  
 **Вызов со скобками**.  Когда процедура `Function` рекурсивно вызывает саму себя, после имени процедуры следует ставить скобки, даже если отсутствует список аргументов.  В противном случае имя функции воспринимается как ее возвращаемое значение.  
  
 **Тестирование**.  Если Вы пишете рекурсивную процедуру, необходимо проверить ее очень внимательно, чтобы убедиться в в том, что она всегда удовлетворяет некоторому граничному условию.  Следует также убедиться в том, что в результате слишком большого количества рекурсивных вызовов вы не израсходуете всю доступную память.  
  
## См. также  
 <xref:System.StackOverflowException>   
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Устранение неполадок в процедурах](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Разрешение вопросов, связанных с исключениями: System.StackOverflowException](../Topic/Troubleshooting%20Exceptions:%20System.StackOverflowException.md)