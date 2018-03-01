---
title: "Безопасность обработки исключений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 548606a0196012fdd21bf5512e8ea7b089c723ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="securing-exception-handling"></a>Безопасность обработки исключений
В Visual C++ и Visual Basic, выражение фильтра, расположенное по стеку, выполняется до любого **наконец** инструкции. **Перехватывать** блок, связанный с этим фильтром, выполняется после **наконец** инструкции. Дополнительные сведения см. в разделе [Using User-Filtered исключения](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). В этом разделе рассматривается влияние на безопасность данного заказа. Рассмотрим следующий пример псевдокода, который иллюстрирует порядок, в которой инструкций фильтра и **наконец** выполнения инструкций.  
  
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
  
 Этот код выводит следующие данные.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 Фильтр выполняется перед **наконец** инструкции, поэтому проблемы безопасности могут быть вызваны все, что состояние может воспользоваться другой код. Пример:  
  
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
  
 В этом псевдокоде фильтр выше в стеке для выполнения произвольного кода. Другие примеры операций, которые будет иметь похожий эффект, являются временная имитация другого удостоверения, установка внутреннего флага, отменяющего некоторые проверки безопасности, или изменение языка и региональных параметров связанного с потоком. Рекомендуемым решением является ввод обработчика исключений для изоляции изменений кода в состояние потока, от блоками фильтрации вызывающего. Тем не менее важно, что исключения правильно установить обработчик, или эта проблема не будет устранена. Следующий пример переключает язык и региональные параметры пользовательского интерфейса, но подобным образом любые изменения состояния потока можно осуществить.  
  
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
  
 Правильным решением в данном случае является программы-оболочки для существующего **повторите**/**наконец** блока в **повторите**/**перехватывать** блок. Простое указание **catch-throw** предложение с существующим **повторите**/**наконец** блок не решает проблему, как показано в следующем примере.  
  
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
  
 Проблема не устраняется, так как **наконец** оператор не выполняется до `FilterFunc` возвращает элемент управления.  
  
 В следующем примере устраняется проблему, проверьте **наконец** предложение выполняется до исключения блоками фильтрации исключений вызывающего.  
  
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
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
