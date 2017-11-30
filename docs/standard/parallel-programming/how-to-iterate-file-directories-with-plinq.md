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
# <a name="how-to-iterate-file-directories-with-plinq"></a><span data-ttu-id="3431b-102">Практическое руководство. Перебор каталогов с файлами с помощью PLINQ</span><span class="sxs-lookup"><span data-stu-id="3431b-102">How to: Iterate File Directories with PLINQ</span></span>
<span data-ttu-id="3431b-103">В этом примере показано два простых способа параллельного выполнения операций на каталоги файлов.</span><span class="sxs-lookup"><span data-stu-id="3431b-103">This example shows two simple ways to parallelize operations on file directories.</span></span> <span data-ttu-id="3431b-104">В первом запросе используется <xref:System.IO.Directory.GetFiles%2A> метод для заполнения массива имен файлов в каталоге и всех его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="3431b-104">The first query uses the <xref:System.IO.Directory.GetFiles%2A> method to populate an array of file names in a directory and all subdirectories.</span></span> <span data-ttu-id="3431b-105">Этот метод не осуществляет возврат, пока весь массив заполняется, и поэтому он может вызывать задержку в начале операции.</span><span class="sxs-lookup"><span data-stu-id="3431b-105">This method does not return until the entire array is populated, and therefore it can introduce latency at the beginning of the operation.</span></span> <span data-ttu-id="3431b-106">Однако после заполнения массива PLINQ может обрабатывать его параллельно очень быстро.</span><span class="sxs-lookup"><span data-stu-id="3431b-106">However, after the array is populated, PLINQ can process it in parallel very quickly.</span></span>  
  
 <span data-ttu-id="3431b-107">Второй запрос использует статические <xref:System.IO.Directory.EnumerateDirectories%2A> и <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> методы, которые начинают сразу возвращать результаты.</span><span class="sxs-lookup"><span data-stu-id="3431b-107">The second query uses the static <xref:System.IO.Directory.EnumerateDirectories%2A> and <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> methods which begin returning results immediately.</span></span> <span data-ttu-id="3431b-108">Этот подход может быть быстрее при перебора деревьев большого каталога, несмотря на то, что по сравнению с в первом примере время обработки может зависеть от многих факторов.</span><span class="sxs-lookup"><span data-stu-id="3431b-108">This approach can be faster when you are iterating over large directory trees, although the processing time compared to the first example can depend on many factors.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3431b-109">Эти примеры предназначены для демонстрации использования и не могут выполняться быстрее, чем эквивалентный последовательный LINQ запрос объектов.</span><span class="sxs-lookup"><span data-stu-id="3431b-109">These examples are intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="3431b-110">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="3431b-110">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3431b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3431b-111">Example</span></span>  
 <span data-ttu-id="3431b-112">В следующем примере показано, как для прохода по каталоги файлов в простых сценариях, когда есть доступ ко всем каталогам в дереве, не очень большой размер файла и время доступа не учитываются.</span><span class="sxs-lookup"><span data-stu-id="3431b-112">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="3431b-113">Этот подход подразумевает задержку в начале, пока создается массив имен файлов.</span><span class="sxs-lookup"><span data-stu-id="3431b-113">This approach involves a period of latency at the beginning while the array of file names is being constructed.</span></span>  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a><span data-ttu-id="3431b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="3431b-114">Example</span></span>  
 <span data-ttu-id="3431b-115">В следующем примере показано, как для прохода по каталоги файлов в простых сценариях, когда есть доступ ко всем каталогам в дереве, не очень большой размер файла и время доступа не учитываются.</span><span class="sxs-lookup"><span data-stu-id="3431b-115">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="3431b-116">При таком подходе результаты появляются быстрее, чем в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3431b-116">This approach begins producing results faster than the previous example.</span></span>  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 <span data-ttu-id="3431b-117">При использовании <xref:System.IO.Directory.GetFiles%2A>, убедитесь, что разрешения достаточны для всех каталогов в дереве.</span><span class="sxs-lookup"><span data-stu-id="3431b-117">When using <xref:System.IO.Directory.GetFiles%2A>, be sure that you have sufficient permissions on all directories in the tree.</span></span> <span data-ttu-id="3431b-118">В противном случае будет вызвано исключение, и результаты не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="3431b-118">Otherwise an exception will be thrown and no results will be returned.</span></span> <span data-ttu-id="3431b-119">При использовании <xref:System.IO.Directory.EnumerateDirectories%2A> в запросе PLINQ довольно трудно обрабатывать исключения ввода-вывода удобным способом, которого можно продолжать перебор.</span><span class="sxs-lookup"><span data-stu-id="3431b-119">When using the <xref:System.IO.Directory.EnumerateDirectories%2A> in a PLINQ query, it is problematic to handle I/O exceptions in a graceful way that enables you to continue iterating.</span></span> <span data-ttu-id="3431b-120">Если код должен обрабатывать ввода-вывода или исключения несанкционированного доступа, то рекомендуется подход, описанный в [как: прохода каталоги файлов с помощью параллельного класса](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).</span><span class="sxs-lookup"><span data-stu-id="3431b-120">If your code must handle I/O or unauthorized access exceptions, then you should consider the approach described in [How to: Iterate File Directories with the Parallel Class](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).</span></span>  
  
 <span data-ttu-id="3431b-121">Если важна задержки ввода-вывода, например с файлового ввода-вывода в сети, можно воспользоваться одним из асинхронного ввода-вывода, описанных в [библиотека параллельных задач и традиционное .NET Framework асинхронное программирование](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) и в этом [записи блога ](http://go.microsoft.com/fwlink/?LinkID=186458).</span><span class="sxs-lookup"><span data-stu-id="3431b-121">If I/O latency is an issue, for example with file I/O over a network, consider using one of the asynchronous I/O techniques described in [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) and in this [blog post](http://go.microsoft.com/fwlink/?LinkID=186458).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3431b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3431b-122">See Also</span></span>  
 [<span data-ttu-id="3431b-123">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="3431b-123">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
