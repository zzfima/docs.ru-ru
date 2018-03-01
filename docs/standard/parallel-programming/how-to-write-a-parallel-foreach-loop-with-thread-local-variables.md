---
title: "Практическое руководство. Написание цикла Parallel.ForEach и локальными переменными потока"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4c65edd8959cbf5f83e3353770f71cad130953d1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-a-parallelforeach-loop-with-thread-local-variables"></a>Практическое руководство. Написание цикла Parallel.ForEach и локальными переменными потока
В следующем примере описывается порядок написания метода <xref:System.Threading.Tasks.Parallel.ForEach%2A>, использующего локальные переменные потока. Когда выполняется цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A>, он делит свою исходную коллекцию на несколько разделов. Каждый раздел получает свою копию локальной переменной потока. (Термин локальная переменная потока употребляется здесь немного неточно, так как в некоторых случаях два раздела могут выполняться в одном потоке.)  
  
 Код и параметры в примере в значительной степени напоминают соответствующий метод <xref:System.Threading.Tasks.Parallel.For%2A>. См. дополнительные сведения о [написании цикла Parallel.For с локальными переменными потока](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md).  
  
 Чтобы использовать локальную переменную потока в цикле <xref:System.Threading.Tasks.Parallel.ForEach%2A>, следует вызвать одну из перегрузок метода, принимающую два параметра типа. Первый параметр типа `TSource` указывает тип исходного элемента, а второй параметр типа `TLocal` указывает тип локальной переменной в потоке.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется вызов перегрузки <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> для вычисления суммы массива, состоящего из одного миллиона элементов. Эта перегрузка имеет четыре параметра:  
  
-   `source`, который обозначает источник данных. Он должен реализовать <xref:System.Collections.Generic.IEnumerable%601>. Источником данных в нашем примере является объект миллионного члена `IEnumerable<Int32>`, возвращенный методом <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType>.  
  
-   `localInit` или функция, инициализирующая локальную переменную потока. Эта функция вызывается для каждого раздела, где выполняется операция <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. В нашем примере локальная переменная потока инициализируется с нулевым значением.  
  
-   `body` — это делегат <xref:System.Func%604>, который вызывается параллельным циклом на каждой итерации данного цикла. Он имеет сигнатуру `Func\<TSource, ParallelLoopState, TLocal, TLocal>`. Вы указываете код для делегата, а цикл передает следующие входные параметры:  
  
    -   Текущий элемент интерфейса <xref:System.Collections.Generic.IEnumerable%601>.  
  
    -   Переменная <xref:System.Threading.Tasks.ParallelLoopState>, которую можно использовать в коде делегата, чтобы определить состояние цикла.  
  
    -   Локальная переменная потока.  
  
     Ваш делегат возвращает локальную переменную потока, которая затем передается в следующую итерацию цикла, выполняемого в данном конкретном разделе. Каждый раздел цикла сохраняет отдельный экземпляр данной переменной.  
  
     В этом примере делегат добавляет значение каждого целого числа в локальную переменную потока, где сохраняется промежуточная сумма значений целочисленных элементов в этом разделе.  
  
-   `localFinally`, делегат `Action<TLocal>`, вызываемый <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> после завершения операций цикла в каждом разделе. Метод <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> передает вашему делегату `Action<TLocal>` окончательное значение локальной переменной потока для данного потока (или раздела цикла), а вы указываете код, который выполняет требуемое действие для объединения результата из данного раздела с результатами из других разделов. Этот делегат может быть одновременно вызван несколькими задачами. В связи с этим в примере используется метод <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> для синхронизации доступа к переменной `total`. Поскольку делегат имеет тип <xref:System.Action%601>, возвращаемое значение отсутствует.  
  
 [!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
 [!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]  
  
## <a name="see-also"></a>См. также  
 [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Практическое руководство. Написание цикла Parallel.For и локальными переменными потока](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)  
 [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
