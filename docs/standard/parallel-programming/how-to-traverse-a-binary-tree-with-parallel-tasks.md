---
title: Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd937d6ce2edf0c47fce78d48a90ec1aa409eef
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44196651"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Практическое руководство. Переход по двоичному дереву с помощью параллельных задач
В следующем примере представлено два способа применить параллельные задачи для обхода древовидной структуры данных. Создание такого дерева остается вам в качестве упражнения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Два представленных здесь метода функционально эквивалентны. Используя метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> для создания и выполнения задач, вы можете получить от этих задач дескриптор и применить его для ожидания задач и обработки исключений.  
  
## <a name="see-also"></a>См. также

- [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
