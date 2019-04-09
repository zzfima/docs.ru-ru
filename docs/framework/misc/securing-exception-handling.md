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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173684"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="8c075-102">Безопасность обработки исключений</span><span class="sxs-lookup"><span data-stu-id="8c075-102">Securing Exception Handling</span></span>
<span data-ttu-id="8c075-103">В Visual C++ и Visual Basic, выражение фильтра, расположенное вверх по стеку, выполняется до любого **наконец** инструкции.</span><span class="sxs-lookup"><span data-stu-id="8c075-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="8c075-104">**Catch** блока, связанного с этим фильтром, выполняется после **наконец** инструкции.</span><span class="sxs-lookup"><span data-stu-id="8c075-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="8c075-105">Дополнительные сведения см. в разделе [Using User-Filtered исключения](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="8c075-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="8c075-106">В этом разделе рассматривается влияние на безопасность этого заказа.</span><span class="sxs-lookup"><span data-stu-id="8c075-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="8c075-107">Рассмотрим следующий пример псевдокода, демонстрирующий порядок, в какие инструкции фильтра и **наконец** запуска инструкций.</span><span class="sxs-lookup"><span data-stu-id="8c075-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="8c075-108">Этот код выводит следующие данные.</span><span class="sxs-lookup"><span data-stu-id="8c075-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="8c075-109">Фильтр выполняется перед **наконец** инструкции, поэтому проблемы безопасности могут быть вызваны все, что делает состояние, в которой может воспользоваться другой код.</span><span class="sxs-lookup"><span data-stu-id="8c075-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="8c075-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="8c075-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="8c075-111">В этом псевдокоде фильтр выше в стеке выполнить произвольный код.</span><span class="sxs-lookup"><span data-stu-id="8c075-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="8c075-112">Другие примеры операций, которые бы к схожим последствиям, временные олицетворение другого удостоверения, установка внутреннего флага, который обходит некоторые проверки безопасности, или смена культуры, ассоциированной с потоком.</span><span class="sxs-lookup"><span data-stu-id="8c075-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="8c075-113">Рекомендуемое решение — представить обработчик исключений для изоляции изменений кода в состоянии потока от блоками фильтрации вызывающего.</span><span class="sxs-lookup"><span data-stu-id="8c075-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="8c075-114">Тем не менее очень важно, что исключения правильно установить обработчик, или эта проблема не будет устранена.</span><span class="sxs-lookup"><span data-stu-id="8c075-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="8c075-115">Следующий пример переключает язык и региональные параметры пользовательского интерфейса, но любые изменения состояния потока могут быть представлены аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="8c075-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="8c075-116">Правильным решением в данном случае является программы-оболочки для существующего **попробуйте**/**наконец** блока в **попробуйте**/**catch** блок.</span><span class="sxs-lookup"><span data-stu-id="8c075-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="8c075-117">Простое указание **catch-throw** предложение с существующими **попробуйте**/**наконец** блок проблема не устранена, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8c075-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8c075-118">Проблема не устранена, так как **наконец** оператор не выполняется до `FilterFunc` Получает элемент управления.</span><span class="sxs-lookup"><span data-stu-id="8c075-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="8c075-119">В следующем примере устраняется проблема, гарантируя, что **наконец** предложение выполняется до исключения блоками фильтрации исключений вызывающего.</span><span class="sxs-lookup"><span data-stu-id="8c075-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c075-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8c075-120">See also</span></span>

- [<span data-ttu-id="8c075-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="8c075-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
