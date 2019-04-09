---
title: Практическое руководство. Как представить столбцы как сформированные базой данных
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2fca0c2fb1d28b5e83902f8664d1c7331774718b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148256"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="569e2-102">Практическое руководство. Как представить столбцы как сформированные базой данных</span><span class="sxs-lookup"><span data-stu-id="569e2-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="569e2-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибут поля или свойства, представляющего столбец, созданный базой данных.</span><span class="sxs-lookup"><span data-stu-id="569e2-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="569e2-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="569e2-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="569e2-105">Назначение поля или свойства, представляющего столбец, созданный базой данных</span><span class="sxs-lookup"><span data-stu-id="569e2-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="569e2-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="569e2-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="569e2-107">В качестве значения свойства задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="569e2-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="569e2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="569e2-108">See also</span></span>

- [<span data-ttu-id="569e2-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="569e2-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="569e2-110">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="569e2-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
