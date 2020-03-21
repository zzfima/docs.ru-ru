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
# <a name="securing-exception-handling"></a>Безопасность обработки исключений
В Visual C и Visual Basic выражение фильтра далее вверх по стеку запускается до того, как **наконец-либо** заявление. Блок **улова,** связанный с этим фильтром, работает **после, наконец,** оператора. Для получения дополнительной [информации см.](../../standard/exceptions/using-user-filtered-exception-handlers.md) В этом разделе рассматриваются последствия этого приказа для безопасности. Рассмотрим следующий пример псевдокода, иллюстрирующий порядок выполнения инструкций фильтра и, **наконец,** инструкций.  
  
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
  
 Этот код печатает следующее.  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 Фильтр работает до **окончательного** оператора, поэтому проблемы безопасности могут быть введены через все, что вносит изменение состояния, где выполнение другого кода может воспользоваться. Пример:  
  
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
  
 Этот псевдокод позволяет фильтру выше стека для запуска произвольного кода. Другими примерами операций, которые будут иметь аналогичный эффект, являются временное олицетворение другого удостоверения, установление внутреннего флага, который обходит некоторую проверку безопасности, или изменение культуры, связанной с потоком. Рекомендуемое решение заключается в введении обработчика исключений для изоляции изменений кода в состоянии потока от блоков фильтров абонентов. Однако важно, чтобы обработчик исключений был надлежащим образом введен или эта проблема не была исправлена. Следующий пример переключает культуру uI, но любое изменение состояния потока может быть также подвержено.  
  
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
  
 Правильное исправление в этом случае заключается в том, чтобы обернуть существующую **попытку,**/**наконец,** блокировать в **блоке поймать попытку.**/**catch** Простое введение оговорки **о броске в** существующую **попытку,**/**наконец,** блокирует не исправляет проблему, как показано в следующем примере.  
  
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
  
 Это не исправляет проблему, поскольку **окончательное** заявление не выполняется до того, как `FilterFunc` получит контроль.  
  
 Следующий пример исправляет проблему, гарантируя, **что, наконец,** оговорка выполнена, прежде чем предлагать исключение вверх блоки фильтра исключения абонентов.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Правила написания безопасного кода](../../standard/security/secure-coding-guidelines.md)
