---
title: Практическое руководство. Как представлять столбцы, допускающие значения NULL
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ef8fa87963b91ef7140fbaefb657fc7904604b5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902919"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="e966b-102">Практическое руководство. Как представлять столбцы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="e966b-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="e966b-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут, чтобы указать, что связанный столбец базы данных может содержать значения null.</span><span class="sxs-lookup"><span data-stu-id="e966b-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="e966b-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="e966b-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="e966b-105">Включение для столбца возможности содержать значения NULL</span><span class="sxs-lookup"><span data-stu-id="e966b-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="e966b-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e966b-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="e966b-107">Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e966b-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e966b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e966b-108">See also</span></span>

- [<span data-ttu-id="e966b-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e966b-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e966b-110">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="e966b-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
