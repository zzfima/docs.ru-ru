---
title: Практическое руководство. Настройка классов сущностей с использованием редактора кода
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: f57b07d03297347561b6b2e2634038aa1f29bc40
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="c2f88-102">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="c2f88-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="c2f88-103">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания или настройки своих классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c2f88-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="c2f88-104">Кроме того, можно использовать в редакторе кода Visual Studio для написания своего кода сопоставления или для настройки уже сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="c2f88-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="c2f88-105">Дополнительные сведения см. в разделе [сопоставления на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c2f88-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="c2f88-106">В подразделах данного раздела описаны способы настройки объектной модели.</span><span class="sxs-lookup"><span data-stu-id="c2f88-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="c2f88-107">Практическое руководство. Указание имен баз данных</span><span class="sxs-lookup"><span data-stu-id="c2f88-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="c2f88-108">Описание использования <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-109">Практическое руководство. Представление таблиц как классов</span><span class="sxs-lookup"><span data-stu-id="c2f88-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="c2f88-110">Описание использования <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="c2f88-111">Практическое руководство. Представление столбцов как членов класса</span><span class="sxs-lookup"><span data-stu-id="c2f88-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="c2f88-112">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="c2f88-113">Практическое руководство. Представление первичных ключей</span><span class="sxs-lookup"><span data-stu-id="c2f88-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="c2f88-114">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-115">Практическое руководство. Сопоставление отношений базы данных</span><span class="sxs-lookup"><span data-stu-id="c2f88-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="c2f88-116">Содержатся примеры использования атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="c2f88-117">Практическое руководство. Представление столбцов как столбцов, созданных базой данных</span><span class="sxs-lookup"><span data-stu-id="c2f88-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="c2f88-118">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-119">Практическое руководство. Представление столбцов как меток времени или столбцов версии</span><span class="sxs-lookup"><span data-stu-id="c2f88-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="c2f88-120">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-121">Практическое руководство. Указание типов данных базы данных</span><span class="sxs-lookup"><span data-stu-id="c2f88-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="c2f88-122">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-123">Практическое руководство. Представление вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="c2f88-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="c2f88-124">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-125">Практическое руководство. Задание частных полей хранения</span><span class="sxs-lookup"><span data-stu-id="c2f88-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="c2f88-126">Описание использования <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-127">Практическое руководство. Представление столбцов как столбцов, допускающих значения NULL</span><span class="sxs-lookup"><span data-stu-id="c2f88-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="c2f88-128">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="c2f88-129">Практическое руководство. Сопоставление иерархий наследования</span><span class="sxs-lookup"><span data-stu-id="c2f88-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="c2f88-130">Описываются сопоставления, необходимые для определения иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="c2f88-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="c2f88-131">Практическое руководство. Задание проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="c2f88-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="c2f88-132">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f88-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f88-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c2f88-133">See Also</span></span>  
 [<span data-ttu-id="c2f88-134">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="c2f88-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
