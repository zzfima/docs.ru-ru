---
title: Безопасность обработки исключений
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181141"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="c0e71-102">Безопасность обработки исключений</span><span class="sxs-lookup"><span data-stu-id="c0e71-102">Securing Exception Handling</span></span>
<span data-ttu-id="c0e71-103">В Visual C и Visual Basic выражение фильтра далее вверх по стеку запускается до того, как **наконец-либо** заявление.</span><span class="sxs-lookup"><span data-stu-id="c0e71-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="c0e71-104">Блок **улова,** связанный с этим фильтром, работает **после, наконец,** оператора.</span><span class="sxs-lookup"><span data-stu-id="c0e71-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="c0e71-105">Для получения дополнительной [информации см.](../../standard/exceptions/using-user-filtered-exception-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="c0e71-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="c0e71-106">В этом разделе рассматриваются последствия этого приказа для безопасности.</span><span class="sxs-lookup"><span data-stu-id="c0e71-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="c0e71-107">Рассмотрим следующий пример псевдокода, иллюстрирующий порядок выполнения инструкций фильтра и, **наконец,** инструкций.</span><span class="sxs-lookup"><span data-stu-id="c0e71-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()
{  
    try
    {  
        Sub();  
    }
    except (Filter())
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()
{  
    try
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }
    finally
    {  
        Console.WriteLine("finally");  
    }  
}
```  
  
 <span data-ttu-id="c0e71-108">Этот код печатает следующее.</span><span class="sxs-lookup"><span data-stu-id="c0e71-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="c0e71-109">Фильтр работает до **окончательного** оператора, поэтому проблемы безопасности могут быть введены через все, что вносит изменение состояния, где выполнение другого кода может воспользоваться.</span><span class="sxs-lookup"><span data-stu-id="c0e71-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="c0e71-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="c0e71-110">For example:</span></span>  
  
```cpp  
try
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and
    // so on) that could be exploited if malicious
    // code ran before state is restored.  
    Do_some_work();  
}
finally
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="c0e71-111">Этот псевдокод позволяет фильтру выше стека для запуска произвольного кода.</span><span class="sxs-lookup"><span data-stu-id="c0e71-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="c0e71-112">Другими примерами операций, которые будут иметь аналогичный эффект, являются временное олицетворение другого удостоверения, установление внутреннего флага, который обходит некоторую проверку безопасности, или изменение культуры, связанной с потоком.</span><span class="sxs-lookup"><span data-stu-id="c0e71-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="c0e71-113">Рекомендуемое решение заключается в введении обработчика исключений для изоляции изменений кода в состоянии потока от блоков фильтров абонентов.</span><span class="sxs-lookup"><span data-stu-id="c0e71-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="c0e71-114">Однако важно, чтобы обработчик исключений был надлежащим образом введен или эта проблема не была исправлена.</span><span class="sxs-lookup"><span data-stu-id="c0e71-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="c0e71-115">Следующий пример переключает культуру uI, но любое изменение состояния потока может быть также подвержено.</span><span class="sxs-lookup"><span data-stu-id="c0e71-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="c0e71-116">Правильное исправление в этом случае заключается в том, чтобы обернуть существующую **попытку,**/**наконец,** блокировать в **блоке поймать попытку.**/**catch**</span><span class="sxs-lookup"><span data-stu-id="c0e71-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="c0e71-117">Простое введение оговорки **о броске в** существующую **попытку,**/**наконец,** блокирует не исправляет проблему, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0e71-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="c0e71-118">Это не исправляет проблему, поскольку **окончательное** заявление не выполняется до того, как `FilterFunc` получит контроль.</span><span class="sxs-lookup"><span data-stu-id="c0e71-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="c0e71-119">Следующий пример исправляет проблему, гарантируя, **что, наконец,** оговорка выполнена, прежде чем предлагать исключение вверх блоки фильтра исключения абонентов.</span><span class="sxs-lookup"><span data-stu-id="c0e71-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try
    {  
        try
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0e71-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0e71-120">See also</span></span>

- [<span data-ttu-id="c0e71-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="c0e71-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
