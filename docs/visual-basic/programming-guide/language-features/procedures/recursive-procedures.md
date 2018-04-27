---
title: Рекурсивные процедуры (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 471746f4412b61c9782e8019aa8a9ec6221afb04
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="recursive-procedures-visual-basic"></a>Рекурсивные процедуры (Visual Basic)
Объект *рекурсивные* процедура является тот, который вызывает саму себя. Как правило это не самый эффективный способ написания кода Visual Basic.  
  
 Следующая процедура использует рекурсию для вычисления факториала исходного аргумента.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Вопросы, связанные с рекурсивные процедуры  
 **Ограничивающие условия**. Необходимо разработать рекурсивную процедуру для проверки на наличие хотя бы одного условия, которое может прервать рекурсию, и вы также должны обрабатывать случаи, когда такое условие не выполняется в течение разумного числа рекурсивных вызовов. Без хотя бы одного условия, которое может быть выполнено без ошибок процедура выполняется высокий риск выполнения в бесконечный цикл.  
  
 **Использование памяти**. Ваше приложение имеет ограниченный объем пространства для локальных переменных. Каждый раз, когда процедура вызывает саму себя, используется больше этого пространства для дополнительных копий ее локальных переменных. Если этот процесс будет продолжаться неопределенно долго, он в конечном итоге вызовет <xref:System.StackOverflowException> ошибки.  
  
 **Эффективность**. Почти всегда можно заменить цикл для рекурсии. Цикл не имеет издержек аргументов передачи, инициализации дополнительного хранилища и возврат значений. Производительность может быть гораздо выше без рекурсивного вызова.  
  
 **Взаимная рекурсия**. Можно наблюдать очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга. Такая конструкция представляет те же проблемы, как одна Рекурсивная процедура, но может быть сложнее обнаружить и отладить.  
  
 **Вызов со скобками**. Когда `Function` процедура вызывает саму себя рекурсивно, следует выполнить имя процедуры в скобки, даже если отсутствует список аргументов. В противном случае имя функции воспринимается как представляющий возвращаемое значение функции.  
  
 **Тестирование**. При написании рекурсивную процедуру, необходимо проверить ее очень внимательно важно убедиться, что он всегда соответствует определенному условию ограничения. Также следует убедиться, не хватает памяти из-за слишком большим количеством рекурсивных вызовов.  
  
## <a name="see-also"></a>См. также  
 <xref:System.StackOverflowException>  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры функций](./function-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Разрешение вопросов, связанных с исключениями: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
