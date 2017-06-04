---
title: "jitCompilationStart MDA | Microsoft Docs"
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
  - "JIT compilation"
  - "MDAs (managed debugging assistants), JIT compilation"
  - "JitCompilationStart MDA"
  - "managed debugging assistants (MDAs), JIT compilation"
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# jitCompilationStart MDA
Управляемый помощник по отладке \(MDA\) `jitCompilationStart` активируется, чтобы сообщить о том, что JIT\-компилятор начал компиляцию функции.  
  
## Признаки  
 Размер рабочего множества для программы увеличивается, даже если она уже в формате исходного образа, поскольку в процесс загружается mscorjit.dll.  
  
## Причина  
 Не все сборки, от которых зависит программа, были сгенерированы в исходный формат, или те сборки, которые были сгенерированы в исходный формат, не были правильно зарегистрированы.  
  
## Решение  
 Включение данного MDA позволяет определить, какие функции были скомпилированы посредством JIT\-компилятора.  Следует определить, была ли сборка, содержащая функцию, сгенерирована в исходном формате и правильно зарегистрирована.  
  
## Влияние на среду выполнения  
 Данный MDA записывает сообщение непосредственно перед компиляцией метода с помощью JIT\-компилятора, поэтому включение данного MDA оказывает значительное влияние на производительность.   Обратите внимание, что если метод является встроенным, данный MDA не будет генерировать отдельное сообщение.  
  
## Output  
 В следующем образце кода приведен пример вывода.   В данном случае результат показывает, что в сборке "Тест" метод "m" класса "ns2.CO" был скомпилирован посредством JIT\-компилятора.  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## Configuration  
 Следующий файл конфигурации содержит различные фильтры, которые можно применять, чтобы отфильтровать методы, о которых будет сообщено при их первой JIT\-компиляции.   Можно определить, что необходимо сообщать обо всех методах, если установить значение атрибута имени равным \*.  
  
```  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 Следующий пример кода необходимо использовать с предыдущим файлом конфигурации:  
  
```  
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)