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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868811"
---
# <a name="securing-exception-handling"></a>Безопасность обработки исключений
В Visual C++ и Visual Basic, выражение фильтра, расположенное вверх по стеку, выполняется до любого **наконец** инструкции. **Catch** блока, связанного с этим фильтром, выполняется после **наконец** инструкции. Дополнительные сведения см. в разделе [Using User-Filtered исключения](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). В этом разделе рассматривается влияние на безопасность этого заказа. Рассмотрим следующий пример псевдокода, демонстрирующий порядок, в какие инструкции фильтра и **наконец** запуска инструкций.  
  
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
  
 Фильтр выполняется перед **наконец** инструкции, поэтому проблемы безопасности могут быть вызваны все, что делает состояние, в которой может воспользоваться другой код. Пример:  
  
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
  
 В этом псевдокоде фильтр выше в стеке выполнить произвольный код. Другие примеры операций, которые бы к схожим последствиям, временные олицетворение другого удостоверения, установка внутреннего флага, который обходит некоторые проверки безопасности, или смена культуры, ассоциированной с потоком. Рекомендуемое решение — представить обработчик исключений для изоляции изменений кода в состоянии потока от блоками фильтрации вызывающего. Тем не менее очень важно, что исключения правильно установить обработчик, или эта проблема не будет устранена. Следующий пример переключает язык и региональные параметры пользовательского интерфейса, но любые изменения состояния потока могут быть представлены аналогичным образом.  
  
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
  
 Правильным решением в данном случае является программы-оболочки для существующего **попробуйте**/**наконец** блока в **попробуйте**/**catch** блок. Простое указание **catch-throw** предложение с существующими **попробуйте**/**наконец** блок проблема не устранена, как показано в следующем примере.  
  
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
  
 Проблема не устранена, так как **наконец** оператор не выполняется до `FilterFunc` Получает элемент управления.  
  
 В следующем примере устраняется проблема, гарантируя, что **наконец** предложение выполняется до исключения блоками фильтрации исключений вызывающего.  
  
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

- [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
