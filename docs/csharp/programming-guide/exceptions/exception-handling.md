---
title: Руководство по программированию на C#. Обработка исключений
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 2ee0e449da89baaa35f3a8a430df6c16fb1e44e4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237939"
---
# <a name="exception-handling-c-programming-guide"></a>Обработка исключений (Руководство по программированию на C#)
Блок [try](../../../csharp/language-reference/keywords/try-catch.md) используется программистами C# для разбиения на разделы кода, который может затрагиваться исключением. Связанные с ним блоки [catch](../../../csharp/language-reference/keywords/try-catch.md) используются для обработки возможных исключений. Блок [finally](../../../csharp/language-reference/keywords/try-finally.md) содержит код, выполняемый вне зависимости от того, вызывается ли исключение в блоке `try`, например для освобождения ресурсов, выделенных в блоке `try`. Блоку `try` требуется один или несколько связанных блоков `catch` или блок `finally` (либо и то, и другое).  
  
 В приведенных ниже примерах показаны операторы `try-catch`, `try-finally` и `try-catch-finally`.  
  
 [!code-csharp[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-csharp[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-csharp[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 Блок `try` без блока `catch` или блока `finally` вызовет ошибку компилятора.  
  
## <a name="catch-blocks"></a>Блоки catch  
 Блок `catch` может определять тип перехватываемого исключения. Спецификация типа называется *фильтром исключений*. Тип исключения должен быть производным от <xref:System.Exception>. Как правило, не следует задавать <xref:System.Exception> в качестве фильтра исключений, кроме случаев, когда известно, как обрабатывать все исключения, которые могут быть вызваны в блоке `try`, или когда оператор [throw](../../../csharp/language-reference/keywords/throw.md) добавлен в конце блока `catch`.  
  
 Несколько блоков `catch` с различными фильтрами исключений могут быть соединены друг с другом. Блоки `catch` проверяются сверху вниз в коде, однако для каждого вызванного исключения выполняется только один блок `catch`. Выполняется первый блок `catch`, в котором указан точный тип или базовый класс вызванного исключения. Если нет блока `catch`, в котором определен соответствующий фильтр исключений, выбирается блок `catch`, в котором не выбран фильтр, если таковой имеется в операторе. Важно, чтобы первыми были размещены блоки `catch` с самыми конкретными (т. е. самыми производными) типами исключений.  
  
 Исключения следует перехватывать при выполнении указанных ниже условий.  
  
-   Вы ясно понимаете возможные причины вызова исключения и можете выполнить восстановление, например, предложив пользователю ввести новое имя файла при перехвате объекта <xref:System.IO.FileNotFoundException>.  
  
-   Вы можете создать и вызвать новое, более конкретное исключение.  
  
     [!code-csharp[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   Требуется частично обработать исключение перед передачей его на дополнительную обработку. В приведенном ниже примере блок `catch` используется для добавления записи в журнал ошибок перед повторным вызовом исключения.  
  
     [!code-csharp[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## <a name="finally-blocks"></a>Блоки "Finally"  
 Блок `finally` позволяет удалить действия, выполненные в блоке `try`. При наличии блока `finally` он выполняется последним, после блока `try` и всех выполняемых блоков `catch`. Блок `finally` выполняется всегда вне зависимости от возникновения исключения или обнаружения блока `catch`, соответствующего типу исключения.  
  
 Блок `finally` можно использовать для высвобождения ресурсов, например потоков данных, подключений к базам данных, графических дескрипторов, не ожидая финализации объектов сборщиком мусора во время выполнения. Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 В приведенном ниже примере с помощью блока `finally` закрывается файл, открытый в блоке `try`. Обратите внимание, что состояние дескриптора файла проверяется до закрытия файла. Если блок `try` не может открыть этот файл, дескриптор файла по-прежнему имеет значение `null`, и блок `finally` не пытается закрыть его. Кроме того, если файл успешно открыт в блоке `try`, блок `finally` закрывает открытый файл.  
  
 [!code-csharp[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделах [Исключения](~/_csharplang/spec/exceptions.md) и [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в [Спецификации языка C#](../../language-reference/language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md)  
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
- [try-finally](../../../csharp/language-reference/keywords/try-finally.md)  
- [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)  
- [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)
