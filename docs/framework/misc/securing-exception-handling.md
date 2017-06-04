---
title: "Securing Exception Handling | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "code security, exception handling"
  - "security [.NET Framework], exception handling"
  - "secure coding, exception handling"
  - "exception handling, security"
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Securing Exception Handling
В Visual C\+\+ и Visual Basic выражение фильтра, расположенное выше по стеку, вычисляется до выполнения любого оператора **finally**.  Блок **catch**, связанный с этим фильтром, выполняется после оператора **finally**.  Дополнительные сведения см. в разделе [Использование исключений, фильтруемых пользователем](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).  В этом разделе рассматриваются вопросы влияния такого порядка на обеспечение безопасности.  Рассмотрим следующий пример псевдокода, который иллюстрирует порядок выполнения операторов фильтров и операторов **finally**.  
  
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
  
 Фильтр выполняется перед оператором **finally**, поэтому любая ситуация, каким\-либо образом изменяющая состояние, может создать проблемы с безопасностью, так как этим может воспользоваться другой код.  Примеры.  
  
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
  
 В этом псевдокоде фильтр, находящийся выше в стеке, может выполнять произвольный код.  Есть и другие примеры операций, в которых достигается аналогичный эффект: временная работа под другой идентификацией, установка внутреннего флага, отменяющего некоторые проверки защиты, смена языка и региональных параметров, связанных с потоком, и т.д.  Рекомендуемое решение — ввести обработчик исключения, изолирующий изменения в состоянии потока кода от блоков фильтрации вызывающих.  Однако важно правильно установить обработчик исключения, иначе решить эту проблему не удастся.  В следующем примере код переключает язык и региональные параметры пользовательского интерфейса, но аналогичным образом возможны и другие изменения состояния потока.  
  
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
  
 Правильным решением в этом случае является включение существующего блока **try**\/**finally** в блок **try**\/**catch**.  Простое указание **catch\-throw** в существующем блоке **try**\/**finally** не решает проблему, как показано в следующем примере.  
  
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
  
 Проблема не решается, так как оператор **finally** не выполняется до тех пор, пока функция `FilterFunc` не получит управление.  
  
 В следующем примере эта проблема устранена, так как оператор **finally** гарантировано выполняется до проверки исключения блоками фильтрации исключений вызывающего.  
  
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
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)