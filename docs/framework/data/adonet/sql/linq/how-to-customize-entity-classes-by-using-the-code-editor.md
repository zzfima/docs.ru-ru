---
title: Как выполнить настроить классы сущностей с помощью редактора кода
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: bef835765120052be388abecde7c3c932c0766e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583237"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="fd8b4-102">Как выполнить настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="fd8b4-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="fd8b4-103">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания или настройки своих классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="fd8b4-104">В редакторе кода Visual Studio также можно написать собственный код сопоставления или настроить код, который уже был создан.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="fd8b4-105">Дополнительные сведения см. в разделе [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="fd8b4-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="fd8b4-106">В подразделах данного раздела описаны способы настройки объектной модели.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="fd8b4-107">Практическое руководство. Указание имен баз данных</span><span class="sxs-lookup"><span data-stu-id="fd8b4-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="fd8b4-108">Описание использования <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-109">Практическое руководство. Представление таблиц как классов</span><span class="sxs-lookup"><span data-stu-id="fd8b4-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="fd8b4-110">Описание использования <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="fd8b4-111">Практическое руководство. Представление столбцов как членов класса</span><span class="sxs-lookup"><span data-stu-id="fd8b4-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="fd8b4-112">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="fd8b4-113">Практическое руководство. Представить первичные ключи</span><span class="sxs-lookup"><span data-stu-id="fd8b4-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="fd8b4-114">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-115">Практическое руководство. Сопоставление отношений базы данных</span><span class="sxs-lookup"><span data-stu-id="fd8b4-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="fd8b4-116">Содержатся примеры использования атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="fd8b4-117">Практическое руководство. Представить столбцы как сформированные базой данных</span><span class="sxs-lookup"><span data-stu-id="fd8b4-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="fd8b4-118">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-119">Практическое руководство. Представить столбцы как отметки времени или столбцов версии</span><span class="sxs-lookup"><span data-stu-id="fd8b4-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="fd8b4-120">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-121">Практическое руководство. Указание типов данных базы данных</span><span class="sxs-lookup"><span data-stu-id="fd8b4-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="fd8b4-122">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-123">Практическое руководство. Представить вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="fd8b4-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="fd8b4-124">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-125">Практическое руководство. Указать поля закрытого хранения</span><span class="sxs-lookup"><span data-stu-id="fd8b4-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="fd8b4-126">Описание использования <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-127">Практическое руководство. Представлять столбцы, допускающие значения Null</span><span class="sxs-lookup"><span data-stu-id="fd8b4-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="fd8b4-128">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="fd8b4-129">Практическое руководство. Сопоставление иерархий наследования</span><span class="sxs-lookup"><span data-stu-id="fd8b4-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="fd8b4-130">Описываются сопоставления, необходимые для определения иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="fd8b4-131">Практическое руководство. Задание проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="fd8b4-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="fd8b4-132">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd8b4-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd8b4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="fd8b4-133">See also</span></span>
- [<span data-ttu-id="fd8b4-134">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="fd8b4-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
