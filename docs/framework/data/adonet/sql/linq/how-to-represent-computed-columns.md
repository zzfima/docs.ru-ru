---
title: Практическое руководство. Как представить вычисляемые столбцы
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 01c3442448285893ebb476ed11889e073065d4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943544"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="564f9-102">Практическое руководство. Как представить вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="564f9-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="564f9-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> для представления столбца, содержимое которого является результатом вычисления.</span><span class="sxs-lookup"><span data-stu-id="564f9-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="564f9-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="564f9-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="564f9-105">не поддерживает вычисляемые столбцы в качестве первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="564f9-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="564f9-106">Представление вычисляемого столбца</span><span class="sxs-lookup"><span data-stu-id="564f9-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="564f9-107">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="564f9-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="564f9-108">Присвойте атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> строковое представление формулы.</span><span class="sxs-lookup"><span data-stu-id="564f9-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564f9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="564f9-109">See also</span></span>

- [<span data-ttu-id="564f9-110">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="564f9-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="564f9-111">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="564f9-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
