---
title: "Практическое руководство. Настройка классов сущностей с использованием редактора кода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d5586e28e784c43488245db814abf32d863232fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="b2e09-102">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="b2e09-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="b2e09-103">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания и настройки своих классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="b2e09-103">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="b2e09-104">Можно также воспользоваться редактором кода [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] для написания своего кода сопоставления или для настройки уже сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="b2e09-104">You can also use the [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="b2e09-105">Дополнительные сведения см. в разделе [сопоставления на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b2e09-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="b2e09-106">В подразделах данного раздела описаны способы настройки объектной модели.</span><span class="sxs-lookup"><span data-stu-id="b2e09-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="b2e09-107">Как: Указание имен баз данных</span><span class="sxs-lookup"><span data-stu-id="b2e09-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="b2e09-108">Описание использования <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-109">Как: представление таблиц как классов</span><span class="sxs-lookup"><span data-stu-id="b2e09-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="b2e09-110">Описание использования <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="b2e09-111">Как: представление столбцов как членов класса</span><span class="sxs-lookup"><span data-stu-id="b2e09-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="b2e09-112">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="b2e09-113">Как: представление первичных ключей</span><span class="sxs-lookup"><span data-stu-id="b2e09-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="b2e09-114">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-115">Как: сопоставление связей базы данных</span><span class="sxs-lookup"><span data-stu-id="b2e09-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="b2e09-116">Содержатся примеры использования атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="b2e09-117">Как: представление столбцов как созданные базой данных</span><span class="sxs-lookup"><span data-stu-id="b2e09-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="b2e09-118">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-119">Как: представление столбцов как меток времени или столбцов версии</span><span class="sxs-lookup"><span data-stu-id="b2e09-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="b2e09-120">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-121">Как: укажите типы данных базы данных</span><span class="sxs-lookup"><span data-stu-id="b2e09-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="b2e09-122">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-123">Как: представление вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="b2e09-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="b2e09-124">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-125">Как: задание частных полей хранения</span><span class="sxs-lookup"><span data-stu-id="b2e09-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="b2e09-126">Описание использования <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-127">Как: представлять столбцы, допускающие значения Null</span><span class="sxs-lookup"><span data-stu-id="b2e09-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="b2e09-128">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="b2e09-129">Как: сопоставление иерархий наследования</span><span class="sxs-lookup"><span data-stu-id="b2e09-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="b2e09-130">Описываются сопоставления, необходимые для определения иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="b2e09-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="b2e09-131">Как: задания проверки конфликт параллелизма</span><span class="sxs-lookup"><span data-stu-id="b2e09-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="b2e09-132">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e09-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e09-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b2e09-133">See Also</span></span>  
 [<span data-ttu-id="b2e09-134">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="b2e09-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
