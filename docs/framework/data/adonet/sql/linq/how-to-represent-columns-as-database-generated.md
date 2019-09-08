---
title: Практическое руководство. Как представить столбцы как сформированные базой данных
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: bb9510986581ad6d3bcd0711aed681ef3a7c4e45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781782"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="b17c2-102">Практическое руководство. Как представить столбцы как сформированные базой данных</span><span class="sxs-lookup"><span data-stu-id="b17c2-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="b17c2-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Используйте<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство атрибута<xref:System.Data.Linq.Mapping.ColumnAttribute> для обозначения поля или свойства, представляющего столбец, сформированный базой данных.</span><span class="sxs-lookup"><span data-stu-id="b17c2-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="b17c2-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="b17c2-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="b17c2-105">Назначение поля или свойства, представляющего столбец, созданный базой данных</span><span class="sxs-lookup"><span data-stu-id="b17c2-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="b17c2-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b17c2-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b17c2-107">В качестве значения свойства задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="b17c2-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17c2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b17c2-108">See also</span></span>

- [<span data-ttu-id="b17c2-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b17c2-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="b17c2-110">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="b17c2-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
