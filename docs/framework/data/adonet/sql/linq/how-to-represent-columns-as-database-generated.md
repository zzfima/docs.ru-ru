---
title: "Практическое руководство. Представление столбцов как столбцов, созданных базой данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a0b36e7035b885985e70203146957cdfca92148b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="a2592-102">Практическое руководство. Представление столбцов как столбцов, созданных базой данных</span><span class="sxs-lookup"><span data-stu-id="a2592-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="a2592-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута назначение поля или свойства, представляющего столбец, созданный базой данных.</span><span class="sxs-lookup"><span data-stu-id="a2592-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="a2592-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2592-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="a2592-105">Назначение поля или свойства, представляющего столбец, созданный базой данных</span><span class="sxs-lookup"><span data-stu-id="a2592-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="a2592-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a2592-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="a2592-107">В качестве значения свойства задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="a2592-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2592-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a2592-108">See Also</span></span>  
 [<span data-ttu-id="a2592-109">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="a2592-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="a2592-110">Как: Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="a2592-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
