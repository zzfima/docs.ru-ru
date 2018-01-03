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
ms.workload: dotnet
ms.openlocfilehash: 6081dd8b6771fc914634f126f7836b4c26147eea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="53956-102">Практическое руководство. Представление столбцов как столбцов, созданных базой данных</span><span class="sxs-lookup"><span data-stu-id="53956-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="53956-103">Используйте [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута назначение поля или свойства, представляющего столбец, созданный базой данных.</span><span class="sxs-lookup"><span data-stu-id="53956-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="53956-104">Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="53956-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="53956-105">Назначение поля или свойства, представляющего столбец, созданный базой данных</span><span class="sxs-lookup"><span data-stu-id="53956-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="53956-106">Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="53956-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="53956-107">В качестве значения свойства задайте `true`.</span><span class="sxs-lookup"><span data-stu-id="53956-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53956-108">См. также</span><span class="sxs-lookup"><span data-stu-id="53956-108">See Also</span></span>  
 [<span data-ttu-id="53956-109">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="53956-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="53956-110">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="53956-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
