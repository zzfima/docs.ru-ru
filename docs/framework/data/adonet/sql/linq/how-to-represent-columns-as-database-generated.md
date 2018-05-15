---
title: Практическое руководство. Представление столбцов как столбцов, созданных базой данных
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: f6b127208ae359b43f273f54d7b5c72933c2eba6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="48cbb-102">Практическое руководство. Представление столбцов как столбцов, созданных базой данных</span><span class="sxs-lookup"><span data-stu-id="48cbb-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="48cbb-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута назначение поля или свойства, представляющего столбец, созданный базой данных.</span><span class="sxs-lookup"><span data-stu-id="48cbb-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="48cbb-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="48cbb-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="48cbb-105">Назначение поля или свойства, представляющего столбец, созданный базой данных</span><span class="sxs-lookup"><span data-stu-id="48cbb-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="48cbb-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="48cbb-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="48cbb-107">В качестве значения свойства задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="48cbb-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48cbb-108">См. также</span><span class="sxs-lookup"><span data-stu-id="48cbb-108">See Also</span></span>  
 [<span data-ttu-id="48cbb-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="48cbb-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="48cbb-110">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="48cbb-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
