---
title: Практическое руководство. Как организовать проверку наличия конфликтов параллелизма
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781590"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="23fd5-102">Практическое руководство. Как организовать проверку наличия конфликтов параллелизма</span><span class="sxs-lookup"><span data-stu-id="23fd5-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="23fd5-103">Можно указать, какие столбцы базы данных должны проверяться на наличие конфликтов параллелизма при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="23fd5-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="23fd5-104">Дополнительные сведения см. в разделе [Практическое руководство. Укажите, какие элементы проверяются на конфликты](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)параллелизма.</span><span class="sxs-lookup"><span data-stu-id="23fd5-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23fd5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="23fd5-105">Example</span></span>  
 <span data-ttu-id="23fd5-106">В следующем примере кода указывается, что член `HomePage` никогда не должен включаться в проверки обновлений.</span><span class="sxs-lookup"><span data-stu-id="23fd5-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="23fd5-107">Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="23fd5-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="23fd5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="23fd5-108">See also</span></span>

- [<span data-ttu-id="23fd5-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="23fd5-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="23fd5-110">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="23fd5-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
