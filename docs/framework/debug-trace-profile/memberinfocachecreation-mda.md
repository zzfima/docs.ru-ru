---
title: "memberInfoCacheCreation MDA | Microsoft Docs"
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
  - "member info cache creation"
  - "MemberInfoCacheCreation MDA"
  - "reflection, run-time errors"
  - "MDAs (managed debugging assistants), cache"
  - "cache [.NET Framework], reflection"
  - "managed debugging assistants (MDAs), cache"
  - "MemberInfo cache"
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# memberInfoCacheCreation MDA
Управляемый помощник по отладке \(MDA\) `memberInfoCacheCreation` активируется при создании кэша <xref:System.Reflection.MemberInfo>.   Как правило, это означает, что программа использует ресурсоемкие функциональные возможности отражения.  
  
## Признаки  
 Рабочее множество программы увеличивается вследствие использования программой ресурсоемких функциональных возможностей отражения.  
  
## Причина  
 Операции отражения, связанные с объектами <xref:System.Reflection.MemberInfo>, относятся к ресурсоемким, поскольку требуется чтение метаданных, которые хранятся в "холодных" страницах, и в целом они указывают на то, что программа использует один из сценариев с поздней привязкой.  
  
## Решение  
 Можно определить место использования функций отражения в программе, включив данный MDA, и затем запустив код в отладчике, либо присоединив отладчик к приложению в момент активации MDA.  В отладчике появится трассировка стека, демонстрирующая место создания кэша <xref:System.Reflection.MemberInfo>, на основании которого можно определить место использования программой функций отражения.  
  
 Решение зависит от целей кода.  Данный MDA предупреждает о том, что программа использует сценарий с поздней привязкой.  Возможно, потребуется определить, следует ли заменить текущий сценарий на сценарий с ранней привязкой, или оставить сценарий с поздней привязкой.  
  
## Влияние на среду выполнения  
 MDA активируется для каждого создаваемого кэша <xref:System.Reflection.MemberInfo>.  Влияние на производительность незначительно.  
  
## Output  
 MDA выводит сообщение, указывающее на создание кэша <xref:System.Reflection.MemberInfo>.  Следует использовать отладчик, чтобы получить трассировку стека, указывающую на место использования программой функций отражения.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 Данный пример кода активирует MDA `memberInfoCacheCreation`:  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## См. также  
 <xref:System.Reflection.MemberInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)