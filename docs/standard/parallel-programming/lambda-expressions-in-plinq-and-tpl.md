---
title: "Lambda Expressions in PLINQ and TPL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Func delegate, creating with lambda expression"
  - "Action delegate, creating with lambda expression"
  - "lambda expressions, with Action and Func"
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Lambda Expressions in PLINQ and TPL
Библиотека параллельных задач \(TPL\) содержит множество методов, которые принимают одно из семейств делегатов <xref:System.Func%601?displayProperty=fullName> или <xref:System.Action?displayProperty=fullName> в качестве входных параметров.  Эти делегаты используются для передачи пользовательской программной логики в параллельный цикл, задачу или запрос.  В примерах кода для библиотеки параллельных задач и в PLINQ для создания экземпляров этих делегатов как встроенных блоков кода используются лямбда\-выражения.  В этой теме приводится краткое введение в делегаты Func и Action и показано использование лямбда\-выражений в библиотеке параллельных задач и PLINQ.  
  
 **Примечание.** Дополнительные общие сведения о делегатах см. в разделах [Делегаты](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md) и [Делегаты](../Topic/Delegates%20\(Visual%20Basic\).md).  Дополнительные сведения о лямбда\-выражениях в C\# и [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] см. в разделах [Лямбда\-выражения](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md) и [Лямбда\-выражения](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md).  
  
## Делегат Func  
 Делегат `Func` инкапсулирует метод, который возвращает значение.  В сигнатуре Func последний или самый правый параметр типа всегда указывает возвращаемый тип.  Одной из наиболее распространенных причин ошибок компилятора является попытка передать два входных параметра в объект <xref:System.Func%602?displayProperty=fullName>; в действительности этот тип получает только один входной параметр.  В библиотеке классов .NET Framework определено 17 версий делегата `Func`: <xref:System.Func%601?displayProperty=fullName>, <xref:System.Func%602?displayProperty=fullName>, <xref:System.Func%603?displayProperty=fullName> и т. д. до <xref:System.Func%6017?displayProperty=fullName>.  
  
## Делегат Action  
 Делегат <xref:System.Action?displayProperty=fullName> инкапсулирует метод \(Sub в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), который не возвращает значение или возвращает значение [void](../Topic/void%20\(C%23%20Reference\).md).  В сигнатуре типа делегата Action параметры типа представляют только входные параметры.  Подобно делегату Func в библиотеке классов .NET Framework определено 17 версий делегата Action: от версии без параметров типа до версии с 16 параметрами типа.  
  
## Пример  
 В следующем примере метода <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=fullName> продемонстрировано выражение делегатов Func и Action с помощью лямбда\-выражений.  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## См. также  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)