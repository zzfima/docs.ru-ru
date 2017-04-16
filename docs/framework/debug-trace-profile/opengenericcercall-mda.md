---
title: "openGenericCERCall MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), CER calls"
  - "open generic CER calls"
  - "constrained execution regions"
  - "openGenericCERCall MDA"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
  - "generics [.NET Framework], open generic CER calls"
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# openGenericCERCall MDA
Помощник по отладке управляемого кода \(MDA\) `openGenericCERCall` активируется для предупреждения о том, что во время JIT\-компиляции или создания образов в машинном коде обрабатывается граф области ограниченного исполнения \(CER\) с переменными универсального типа в корневом методе; и, по крайней мере, одна из переменных универсального типа является переменной ссылочного типа на объект.  
  
## Признаки  
 Код в области CER не выполняется при аварийном завершении работы потока или при выгрузке домена приложения.  
  
## Причина  
 Во время JIT\-компиляции экземпляры, содержащие ссылочный тип на объект, являются лишь репрезентативными, поскольку результирующий код является общим и все переменные ссылочного типа на объект могут относиться к любому ссылочному типу на объект.  Это может помешать предварительной подготовке некоторых ресурсов времени выполнения.  
  
 В частности, методы с переменными универсального типа могут выполнять отложенное размещение ресурсов в фоновом режиме.  Данные методы называются универсальными записями словаря.  Например, для оператора `List<T> list = new List<T>();` , где `T` является переменной универсального типа, среда выполнения должна выполнить поиск и, возможно, создание точного экземпляра в среде выполнения, например `List<Object>, List<String>`, и т. д.  Это может оказаться невозможным по ряду причин, не зависящих от разработчика, например вследствие нехватки памяти.  
  
 Данный помощник по отладке управляемого кода должен быть активирован только во время JIT\-компиляции, а не при создании точного экземпляра.  
  
 При активации данного помощник по отладке управляемого кода вероятным симптомом является неработоспособность областей ограниченного исполнения для поврежденных экземпляров.  Фактически, среда выполнения не пытается реализовать область CER в условиях, вызвавших активацию помощника по отладке управляемого кода.  Таким образом, если разработчик использует общий экземпляр области CER, ошибки JIT\-компиляции, ошибки загрузки универсального типа или аварийные завершения работы потока в предполагаемой области CER перехватываться не будут.  
  
## Решение  
 Не следует использовать переменные универсального типа, относящиеся к ссылочному типу на объект, для методов, которые могут содержать область CER.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  
  
## Output  
 Следующий пример демонстрирует результат действия данного помощника по отладке управляемого кода:  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 Код CER не выполняется.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Runtime.CompilerServices;  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        CallGenericMethods();  
    }  
    static void CallGenericMethods()  
    {  
        // This call is correct. The instantiation of the method  
        // contains only nonreference types.  
        MyClass.GenericMethodWithCer<int>();  
  
        // This call is incorrect. A shared version of the method that  
        // cannot be completely analyzed will be JIT-compiled. The   
        // MDA will be activated at JIT-compile time, not at run time.  
        MyClass.GenericMethodWithCer<String>();  
    }  
}  
  
    class MyClass  
{  
    public static void GenericMethodWithCer<T>()  
    {  
        RuntimeHelpers.PrepareConstrainedRegions();  
        try  
        {  
  
        }  
        finally  
        {  
            // This is the start of the CER.  
            Console.WriteLine("In finally block.");  
        }  
    }  
}  
```  
  
## См. также  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)