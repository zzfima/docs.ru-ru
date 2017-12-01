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
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
В следующем примере показано два способа, в которых параллельных задач можно использовать для обхода древовидной структуре данных. Создание дерева остается в качестве упражнения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Два представленных метода функционально эквивалентны. С помощью <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> метод для создания и выполнения этих задач, можно получить дескриптор обратно из задач, которые можно использовать для ожидания задач и обработки исключений.  
  
## <a name="see-also"></a>См. также  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
