---
title: Практическое руководство. Как настроить классы сущностей с помощью редактора кода
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 67a0e17b6a81d804ce101bf56d8da82fe330479c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743424"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="bf5c8-102">Практическое руководство. Как настроить классы сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="bf5c8-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="bf5c8-103">Разработчики, использующие Visual Studio можно использовать реляционный конструктор объектов для создания или настройки своих классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="bf5c8-104">В редакторе кода Visual Studio также можно написать собственный код сопоставления или настроить код, который уже был создан.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="bf5c8-105">Дополнительные сведения см. в разделе [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="bf5c8-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="bf5c8-106">В подразделах данного раздела описаны способы настройки объектной модели.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="bf5c8-107">Практическое руководство. Указание имен баз данных</span><span class="sxs-lookup"><span data-stu-id="bf5c8-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="bf5c8-108">Описание использования <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-109">Практическое руководство. Представление таблиц как классов</span><span class="sxs-lookup"><span data-stu-id="bf5c8-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="bf5c8-110">Описание использования <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="bf5c8-111">Практическое руководство. Представление столбцов как членов класса</span><span class="sxs-lookup"><span data-stu-id="bf5c8-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="bf5c8-112">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="bf5c8-113">Практическое руководство. Представить первичные ключи</span><span class="sxs-lookup"><span data-stu-id="bf5c8-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="bf5c8-114">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-115">Практическое руководство. Сопоставление отношений базы данных</span><span class="sxs-lookup"><span data-stu-id="bf5c8-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="bf5c8-116">Содержатся примеры использования атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="bf5c8-117">Практическое руководство. Представить столбцы как сформированные базой данных</span><span class="sxs-lookup"><span data-stu-id="bf5c8-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="bf5c8-118">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-119">Практическое руководство. Представить столбцы как отметки времени или столбцов версии</span><span class="sxs-lookup"><span data-stu-id="bf5c8-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="bf5c8-120">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-121">Практическое руководство. Указание типов данных базы данных</span><span class="sxs-lookup"><span data-stu-id="bf5c8-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="bf5c8-122">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-123">Практическое руководство. Представить вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="bf5c8-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="bf5c8-124">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-125">Практическое руководство. Указать поля закрытого хранения</span><span class="sxs-lookup"><span data-stu-id="bf5c8-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="bf5c8-126">Описание использования <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-127">Практическое руководство. Представлять столбцы, допускающие значения Null</span><span class="sxs-lookup"><span data-stu-id="bf5c8-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="bf5c8-128">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="bf5c8-129">Практическое руководство. Сопоставление иерархий наследования</span><span class="sxs-lookup"><span data-stu-id="bf5c8-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="bf5c8-130">Описываются сопоставления, необходимые для определения иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="bf5c8-131">Практическое руководство. Задание проверки на конфликты параллельности</span><span class="sxs-lookup"><span data-stu-id="bf5c8-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="bf5c8-132">Описание использования <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf5c8-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5c8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="bf5c8-133">See also</span></span>

- [<span data-ttu-id="bf5c8-134">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="bf5c8-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
