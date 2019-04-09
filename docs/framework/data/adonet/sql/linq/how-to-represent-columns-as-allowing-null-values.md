---
title: Практическое руководство. Как представлять столбцы, допускающие значения NULL
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: e3bab3f307bcba77e0d311b96fa79d5a0d01e937
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169641"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="80b06-102">Практическое руководство. Как представлять столбцы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="80b06-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="80b06-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы указать, что связанный столбец базы данных может содержать значения null.</span><span class="sxs-lookup"><span data-stu-id="80b06-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="80b06-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="80b06-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="80b06-105">Включение для столбца возможности содержать значения NULL</span><span class="sxs-lookup"><span data-stu-id="80b06-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="80b06-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80b06-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="80b06-107">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="80b06-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b06-108">См. также</span><span class="sxs-lookup"><span data-stu-id="80b06-108">See also</span></span>

- [<span data-ttu-id="80b06-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="80b06-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="80b06-110">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="80b06-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
