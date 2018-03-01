---
title: "Практическое руководство. Переход по двоичному дереву с помощью параллельных задач"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0196d82dd46a105f7cf1db0f9333a5d28afe559b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
В следующем примере представлено два способа применить параллельные задачи для обхода древовидной структуры данных. Создание такого дерева остается вам в качестве упражнения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Два представленных здесь метода функционально эквивалентны. Используя метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> для создания и выполнения задач, вы можете получить от этих задач дескриптор и применить его для ожидания задач и обработки исключений.  
  
## <a name="see-also"></a>См. также  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
