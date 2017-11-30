---
title: "Практическое руководство. Задание проверки на конфликты параллельности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e9c3839f4b70bfec759617d875095d9ce8eecf54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="c224f-102">Практическое руководство. Задание проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="c224f-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="c224f-103">Можно указать, какие столбцы базы данных должны проверяться на наличие конфликтов параллелизма при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="c224f-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="c224f-104">Дополнительные сведения см. в разделе [как: укажите каких элементов проверяются на наличие конфликтов параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="c224f-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c224f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c224f-105">Example</span></span>  
 <span data-ttu-id="c224f-106">В следующем примере кода указывается, что член `HomePage` никогда не должен включаться в проверки обновлений.</span><span class="sxs-lookup"><span data-stu-id="c224f-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="c224f-107">Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="c224f-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c224f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c224f-108">See Also</span></span>  
 [<span data-ttu-id="c224f-109">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="c224f-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="c224f-110">Как: Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="c224f-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
