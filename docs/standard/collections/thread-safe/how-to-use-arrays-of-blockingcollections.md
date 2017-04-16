---
title: "Практическое руководство. Использование массивов для блокировки коллекций в конвейере | Microsoft Docs"
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
  - "потокобезопасные коллекции, блокировка коллекций в конвейере"
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Использование массивов для блокировки коллекций в конвейере
В следующем примере показано как использовать массив объектов <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> со статическими методами, например, методом <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> и методом <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, для реализации быстрой и гибкой передачи данных между компонентами.  
  
## Пример  
 В следующем примере показана основная реализация конвейера, в котором каждый объект выполняет параллельную операцию получения данных из входной коллекции, выполняет их преобразование и передает их в выходную коллекцию.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)