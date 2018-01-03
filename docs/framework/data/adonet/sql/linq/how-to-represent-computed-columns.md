---
title: "Практическое руководство. Представление вычисляемых столбцов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 42afded36f6006f369dfddb7ed3a51598b3fc33a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="7ce4d-102">Практическое руководство. Представление вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="7ce4d-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="7ce4d-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, представляющего столбец, содержимое которого являются результатом вычисления.</span><span class="sxs-lookup"><span data-stu-id="7ce4d-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="7ce4d-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ce4d-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="7ce4d-105"> не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="7ce4d-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="7ce4d-106">Представление вычисляемого столбца</span><span class="sxs-lookup"><span data-stu-id="7ce4d-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="7ce4d-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7ce4d-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="7ce4d-108">Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.</span><span class="sxs-lookup"><span data-stu-id="7ce4d-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce4d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce4d-109">See Also</span></span>  
 [<span data-ttu-id="7ce4d-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7ce4d-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="7ce4d-111">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="7ce4d-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
