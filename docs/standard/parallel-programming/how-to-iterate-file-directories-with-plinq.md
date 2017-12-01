---
title: "Практическое руководство. Перебор каталогов с файлами с помощью PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Практическое руководство. Перебор каталогов с файлами с помощью PLINQ
В этом примере показано два простых способа параллельного выполнения операций на каталоги файлов. В первом запросе используется <xref:System.IO.Directory.GetFiles%2A> метод для заполнения массива имен файлов в каталоге и всех его подкаталогах. Этот метод не осуществляет возврат, пока весь массив заполняется, и поэтому он может вызывать задержку в начале операции. Однако после заполнения массива PLINQ может обрабатывать его параллельно очень быстро.  
  
 Второй запрос использует статические <xref:System.IO.Directory.EnumerateDirectories%2A> и <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> методы, которые начинают сразу возвращать результаты. Этот подход может быть быстрее при перебора деревьев большого каталога, несмотря на то, что по сравнению с в первом примере время обработки может зависеть от многих факторов.  
  
> [!WARNING]
>  Эти примеры предназначены для демонстрации использования и не могут выполняться быстрее, чем эквивалентный последовательный LINQ запрос объектов. Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для прохода по каталоги файлов в простых сценариях, когда есть доступ ко всем каталогам в дереве, не очень большой размер файла и время доступа не учитываются. Этот подход подразумевает задержку в начале, пока создается массив имен файлов.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для прохода по каталоги файлов в простых сценариях, когда есть доступ ко всем каталогам в дереве, не очень большой размер файла и время доступа не учитываются. При таком подходе результаты появляются быстрее, чем в предыдущем примере.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 При использовании <xref:System.IO.Directory.GetFiles%2A>, убедитесь, что разрешения достаточны для всех каталогов в дереве. В противном случае будет вызвано исключение, и результаты не возвращаются. При использовании <xref:System.IO.Directory.EnumerateDirectories%2A> в запросе PLINQ довольно трудно обрабатывать исключения ввода-вывода удобным способом, которого можно продолжать перебор. Если код должен обрабатывать ввода-вывода или исключения несанкционированного доступа, то рекомендуется подход, описанный в [как: прохода каталоги файлов с помощью параллельного класса](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Если важна задержки ввода-вывода, например с файлового ввода-вывода в сети, можно воспользоваться одним из асинхронного ввода-вывода, описанных в [библиотека параллельных задач и традиционное .NET Framework асинхронное программирование](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) и в этом [записи блога ](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## <a name="see-also"></a>См. также  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
