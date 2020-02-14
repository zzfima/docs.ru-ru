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
ms.openlocfilehash: e0465f2eb6be61e161f5e6b8cadf629a53f11906
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215790"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="48f00-102">Безопасность обработки исключений</span><span class="sxs-lookup"><span data-stu-id="48f00-102">Securing Exception Handling</span></span>
<span data-ttu-id="48f00-103">В Visual C++ и Visual Basic выражение фильтра, расположенное дальше вверх по стеку, выполняется перед любым оператором **finally** .</span><span class="sxs-lookup"><span data-stu-id="48f00-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="48f00-104">Блок **catch** , связанный с этим фильтром, выполняется после оператора **finally** .</span><span class="sxs-lookup"><span data-stu-id="48f00-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="48f00-105">Дополнительные сведения см. [в разделе Использование исключений с пользовательской фильтрацией](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="48f00-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="48f00-106">В этом разделе рассматриваются аспекты безопасности в этом порядке.</span><span class="sxs-lookup"><span data-stu-id="48f00-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="48f00-107">Рассмотрим следующий пример псевдокода, демонстрирующий порядок выполнения операторов Filter и операторов **finally** .</span><span class="sxs-lookup"><span data-stu-id="48f00-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="48f00-108">Этот код выводит следующие фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="48f00-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="48f00-109">Фильтр выполняется перед оператором **finally** , поэтому проблемы безопасности могут быть сделаны любыми, которые делают изменение состояния, когда выполнение другого кода может воспользоваться преимуществами.</span><span class="sxs-lookup"><span data-stu-id="48f00-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="48f00-110">Например:</span><span class="sxs-lookup"><span data-stu-id="48f00-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="48f00-111">Этот псевдокод позволяет использовать фильтр выше в стеке для выполнения произвольного кода.</span><span class="sxs-lookup"><span data-stu-id="48f00-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="48f00-112">Другие примеры операций, которые будут иметь подобный результат, — это временное олицетворение другого удостоверения, установка внутреннего флага, который обходит некоторую проверку безопасности, или изменение языка и региональных параметров, связанных с потоком.</span><span class="sxs-lookup"><span data-stu-id="48f00-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="48f00-113">Рекомендуемым решением является ввод обработчика исключений для изоляции изменений кода от блоков фильтра вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="48f00-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="48f00-114">Однако важно правильно представить обработчик исключений, иначе эта проблема не будет исправлена.</span><span class="sxs-lookup"><span data-stu-id="48f00-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="48f00-115">В следующем примере переключается язык и региональные параметры пользовательского интерфейса, но любой тип изменения состояния потока может быть аналогичным.</span><span class="sxs-lookup"><span data-stu-id="48f00-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="48f00-116">Правильным исправлением в этом случае является заключение существующего блока **try**/**finally** в блок **try**/**catch** .</span><span class="sxs-lookup"><span data-stu-id="48f00-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="48f00-117">Простое введение предложения **catch-throw** в существующий блок **try**/**finally** не устраняет проблему, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="48f00-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="48f00-118">Это не устраняет проблему, так как оператор **finally** не выполнялся до того, как `FilterFunc` получает управление.</span><span class="sxs-lookup"><span data-stu-id="48f00-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="48f00-119">Следующий пример устраняет проблему, гарантируя, что предложение **finally** выполнялось до того, как будет предложено исключение в блоках фильтра исключений вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="48f00-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48f00-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="48f00-120">See also</span></span>

- [<span data-ttu-id="48f00-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="48f00-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
