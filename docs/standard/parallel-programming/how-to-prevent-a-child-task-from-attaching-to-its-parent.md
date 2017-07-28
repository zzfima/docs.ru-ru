---
title: "How to: Prevent a Child Task from Attaching to its Parent | Microsoft Docs"
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
  - "tasks, preventing attachments"
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Prevent a Child Task from Attaching to its Parent
В этом документе показано, как предотвратить прикрепление дочерней задачи к родительской.  Предотвращение прикрепления дочерней задачи к родительской полезно при вызове компонентов, написанным сторонним разработчиком и также использующим задачи.  Например, компонент третьей стороны, использующий параметр <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> для создания объекта <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>, может вызвать проблемы в коде, если он продолжительный или генерирует необрабатываемое исключение.  
  
## Пример  
 В следующем примере сравниваются последствия использования параметров по умолчанию с последствиями от предотвращения прикрепления дочерней задачи к родительской.  В примере создается объект <xref:System.Threading.Tasks.Task>, вызывающий библиотеку третьей стороны, которая также использует объект <xref:System.Threading.Tasks.Task>.  Библиотека третьей стороны использует параметр <xref:System.Threading.Tasks.TaskCreationOptions> для создания объекта <xref:System.Threading.Tasks.Task>.  Приложение использует параметр <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> для создания родительской задачи.  Этот параметр указывает среде выполнения удалить спецификацию <xref:System.Threading.Tasks.TaskCreationOptions> в дочерних задачах.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Поскольку родительская задача не завершается, пока все дочерние задачи не будет завершены, длительная дочерняя задача может привести к ухудшению производительности приложения в целом.  В этом примере, когда приложение использует параметры по умолчанию для создания родительской задачи, дочерняя задача должна выполниться до завершения родительской задачи.  Когда приложение использует параметр <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName>, дочерняя задача не будет прикреплен к родительской.  Поэтому приложение может выполнять дополнительную работу после завершения родительской задачи и до ожидания завершения дочерней задачи.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DenyChildAttach.cs` \(`DenyChildAttach.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## Отказоустойчивость  
  
## См. также  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)