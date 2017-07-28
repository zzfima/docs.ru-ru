---
title: "How to: Traverse a Binary Tree with Parallel Tasks | Microsoft Docs"
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
  - "tasks, how to traverse a tree"
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Traverse a Binary Tree with Parallel Tasks
В следующем примере показано два способа использования параллельных задач для перемещения по древовидной структуре данных.  Создание дерева предлагается выполнить в качестве упражнения.  
  
## Пример  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Два представленных метода функционально эквивалентны.  Используя метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> для создания и выполнения этих задач, можно получить обратно из задач маркер для ожидания задач и обработки исключений.  
  
## См. также  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)