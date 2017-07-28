---
title: "Reliability | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SQL Server [.NET Framework]"
  - "managed code, reliability"
  - "reliability [.NET Framework]"
  - "writing reliable code"
  - "code, reliability"
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Reliability
Важным аспектом является защита кода, выполняемого в средах сервера, например SQL Server, от асинхронных исключений.  Надежность, как она понимается в этом обсуждении, относится не столько к SQL Server, сколько к созданию надежного кода для любого основного приложения, выполняющегося в среде .NET Framework версии 2.0.  Однако SQL Server — это первая служба, в которой стали широко использоваться новые функциональные возможности версии 2.0, связанные с надежностью, поэтому именно этот сервер взят в качестве примера.  
  
 Код, выполняющийся на SQL Server должен соответствовать более строгим правилам надежности в отличие от других серверных сред.  Это связано с устойчивыми операциями SQL Server, использующими минимально возможное количество ресурсов. <xref:System.OutOfMemoryException> и исключения <xref:System.Threading.ThreadAbortException> не являются нехарактерными для среды SQL Server.  В целом, эти правила связаны не столько с надежностью, сколько с разрешением корректного сбоя управляемого кода с полным доверием перед возможностью повторного использования на уровне <xref:System.AppDomain>, что является основным способом поддержки стабильности и доступности данных на сервере.  
  
## В этом подразделе  
 [SQL Server Programming and Host Protection Attributes](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Описание использования атрибута <xref:System.Security.Permissions.HostProtectionAttribute> в SQL Server для ограничения выполнения управляемого кода.  
  
 [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md)  
 Предоставление правил создания кода, соответствующего требованиям надежности.  
  
 [Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)  
 Описание функции и поведения областей CER.  
  
## Ссылка  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>