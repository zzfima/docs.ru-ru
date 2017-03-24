---
title: "Рекурсивные процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fc95cd5f7cfd5637f6282c6ef571eb81bac1816
ms.lasthandoff: 03/13/2017

---
# <a name="recursive-procedures-visual-basic"></a>Рекурсивные процедуры (Visual Basic)
Объект *рекурсивного* — процедура, которая вызывает сама себя. Как правило, это не самый эффективный способ написания [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода.  
  
 Следующая процедура использует рекурсию для вычисления факториала исходного аргумента.  
  
 [!code-vb[VbVbcnProcedures&#51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Вопросы, связанные с рекурсивные процедуры  
 **Ограничивающие условия**. Необходимо разработать рекурсивную процедуру для проверки по крайней мере одного условия, которое может прервать рекурсию, и вы также должны обрабатывать случаи, когда такое условие не выполняется в течение разумного числа рекурсивных вызовов. Без хотя бы одного условия, которое может быть выполнено без ошибок процедура выполняется высокий риск выполнения в бесконечном цикле.  
  
 **Использование памяти**. Приложение имеет ограниченный объем пространства для локальных переменных. Каждый раз, когда процедура вызывает саму себя, используется больше этого пространства для дополнительных копий ее локальных переменных. Если этот процесс будет продолжаться неопределенно долго, он в конечном итоге вызовет <xref:System.StackOverflowException>ошибка.</xref:System.StackOverflowException>  
  
 **Эффективность**. Почти всегда можно заменить цикл для рекурсии. Цикл не имеет дополнительных издержек аргументов передачи, инициализации дополнительного хранилища и возврат значений. Производительность может быть гораздо выше без рекурсивного вызова.  
  
 **Взаимная рекурсия**. Можно наблюдать очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга. Такой макет представляет те же проблемы, как одна Рекурсивная процедура, но может быть сложнее обнаружить и отладить.  
  
 **Вызов со скобками**. Когда `Function` процедура вызывает себя рекурсивно, необходимо выполнить процедуру имя со скобками, даже если отсутствует список аргументов. В противном случае — берется имя функции, представляющего возвращаемое значение функции.  
  
 **Тестирование**. Если вы пишете рекурсивную процедуру, следует проверить ее очень внимательно, чтобы убедиться, что он всегда условие некоторые ограничения. Следует также убедиться, что не может работать не хватает памяти из-за слишком большим количеством рекурсивных вызовов.  
  
## <a name="see-also"></a>См. также  
 <xref:System.StackOverflowException></xref:System.StackOverflowException>   
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры функций](./function-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Перегрузка процедур](./procedure-overloading.md)   
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Разрешение вопросов, связанных с исключениями: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
