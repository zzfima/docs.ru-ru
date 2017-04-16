---
title: "illegalPrepareConstrainedRegion MDA | Microsoft Docs"
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
  - "PrepareConstrainedRegions method"
  - "managed debugging assistants (MDAs), illegal PrepareConstrainedRegions"
  - "try/catch exception handling, managed debugging assistants"
  - "IllegalPrepareConstrainedRegions MDA"
  - "MDAs (managed debugging assistants), illegal PrepareConstrainedRegions"
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# illegalPrepareConstrainedRegion MDA
Управляемый помощник по отладке \(MDA\) `illegalPrepareConstrainedRegion` активируется, если метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> не предшествует непосредственно оператору `try` обработчика исключений.  Данное ограничение находится на уровне MSIL, поэтому допускается использование текста, не создающего код, между вызовом и использованием `try`, — например, комментариев.  
  
## Признаки  
 Область с ограничением исполнения \(CER\), которая никогда не обрабатывалась как таковая, но рассматривалась как блок обработки исключений \(`finally` или `catch`\).  Как следствие, код в этой области не выполняется в случае недостаточности памяти или прерывания потока.  
  
## Причина  
 Образец подготовки для CER не был должным образом соблюден.  Это является ошибкой.  Вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, используемого, чтобы помечать обработчики исключений как представляющие CER в своих блоках `catch`\/`finally`\/`fault`\/`filter`, должен выполняться непосредственно перед оператором `try`.  
  
## Решение  
 Следует убедиться, что вызов <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> выполняется непосредственно перед оператором `` `try`.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  
  
## Output  
 MDA отображает имя метода, вызывающего метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, смещение MSIL и сообщение о том, что вызов не предшествовал непосредственно блоку "try".  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода демонстрируется шаблон, который вызывает активацию MDA:  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)