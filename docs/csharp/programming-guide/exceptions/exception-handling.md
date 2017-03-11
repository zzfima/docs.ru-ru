---
title: "Обработка исключений (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "обработка исключений [C#], об обработке исключений"
  - "исключения [C#], обработка"
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Обработка исключений (Руководство по программированию на C#)
Блок [try](../../../csharp/language-reference/keywords/try-catch.md) используется программистами C\# для разбиения на разделы кода, который может затрагиваться исключением.  Связанные с ним блоки [поймать](../../../csharp/language-reference/keywords/try-catch.md) используются для обработки возможных исключений.  Блок [finally](../../../csharp/language-reference/keywords/try-finally.md), содержащий код, выполняемый вне зависимости от того, вызвано ли исключение в блоке `try`, например освобождение ресурсов, выделенных блоку `try`.  Блоку `try` требуется один или несколько связанных блоков `catch` или блок `finally` \(либо и то, и другое\).  
  
 Следующие примеры показывают операторы `try-catch`, `try-finally` и `try-catch-finally`.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_3.cs)]  
  
 Блок `try` без блока `catch` или блока `finally` вызовет ошибку компилятора.  
  
## Блоки catch  
 Блок `catch` может указывать тип перехватываемого исключения.  Спецификация типа называется *фильтр исключений*.  Тип исключения должны быть унаследован от <xref:System.Exception>.  Как правило, не следует задавать <xref:System.Exception> в качестве фильтра исключений, кроме случаев, когда известно, как обрабатывать  все исключения, которые могут быть созданы в блоке `try`, и когда оператор [throw](../../../csharp/language-reference/keywords/throw.md) вставлен в конце блока `catch`.  
  
 Несколько блоков `catch` с различными фильтрами исключений могут быть соединены друг с другом.  Блоки `catch` проверяются сверху вниз в коде, однако для каждого вызванного исключения выполняется только один блок `catch`.  Выполняется первый блок `catch`, указывающий точный тип или базовый класс созданного исключения.  Если нет блока `catch`, который определяет соответствующий фильтр исключений, выбирается блок `catch`, в котором не выбран фильтр, если таковой имеется в операторе.  Очень важно, чтобы первыми были размещены блоки `catch` с самыми конкретными \(т. е., самыми производными\) типами исключений.  
  
 Перехват исключений возможен при выполнении следующих условий.  
  
-   Имеется хорошее понимание причин создания исключения, имеются навыки выполнения специального восстановления, например путем предложения пользователю ввести новое имя файла при перехвате объекта <xref:System.IO.FileNotFoundException>.  
  
-   Возможность создания и вызова нового, более конкретного исключения.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_4.cs)]  
  
-   Требуется частично обработать исключение перед передачей его на дополнительную обработку.  В следующем примере блок `catch` используется для добавления записи в журнал ошибок перед повторным вызовом исключения.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_5.cs)]  
  
## Блоки finally  
 Блок `finally` позволяет удалить действия, выполненные в блоке `try`.  При наличии блока `finally` он выполняется последним, после блока `try` и всех выполняемых блоков `catch`.  Блок `finally` выполняется всегда, вне зависимости от возникновения исключения или обнаружения блока `catch`, соответствующего типу исключения.  
  
 Блок `finally` можно использовать для высвобождения ресурсов, например потоков данных, подключений к базам данных, графических дескрипторов, не ожидая финализации объектов сборщиком мусора в среде выполнения.  Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 В следующем примере с помощью блока `finally` закрывается файл, открытый в блоке `try`.  Обратите внимание, что состояние дескриптора файла проверяется до закрытия файла.  Если блок `try` не может открыть этот файл, дескриптор файла по\-прежнему имеет значение `null` и блок `finally` не пытается закрыть его.  Кроме того, если файл успешно открыт в блоке `try`, блок `finally` закрывает открытый файл.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_6.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)