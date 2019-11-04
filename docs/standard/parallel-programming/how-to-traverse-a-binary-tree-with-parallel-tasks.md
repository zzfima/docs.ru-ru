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
ms.openlocfilehash: b79337e6ee8057506ff87c696cecd6b038eeebfc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141643"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="a3550-102">Практическое руководство. Переход по двоичному дереву с помощью параллельных задач</span><span class="sxs-lookup"><span data-stu-id="a3550-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="a3550-103">В следующем примере представлено два способа применить параллельные задачи для обхода древовидной структуры данных.</span><span class="sxs-lookup"><span data-stu-id="a3550-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="a3550-104">Создание такого дерева остается вам в качестве упражнения.</span><span class="sxs-lookup"><span data-stu-id="a3550-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3550-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a3550-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="a3550-106">Два представленных здесь метода функционально эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="a3550-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="a3550-107">Используя метод <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> для создания и выполнения задач, вы можете получить от этих задач дескриптор и применить его для ожидания задач и обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="a3550-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3550-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a3550-108">See also</span></span>

- [<span data-ttu-id="a3550-109">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="a3550-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
