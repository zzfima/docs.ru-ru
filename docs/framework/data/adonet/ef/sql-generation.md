---
title: Создание SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 2c18e88967fcba2b8414bfc171412eba908002b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248404"
---
# <a name="sql-generation"></a><span data-ttu-id="ca03f-102">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="ca03f-102">SQL Generation</span></span>
<span data-ttu-id="ca03f-103">При написании поставщика для [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] необходимо перевести дерево команд [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] на язык SQL, понятный базе данных, например Transact-SQL для SQL Server или PL/SQL для Oracle.</span><span class="sxs-lookup"><span data-stu-id="ca03f-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="ca03f-104">В этом разделе описано, как разрабатывать компонент создания кода SQL (для запросов SELECT) для поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca03f-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="ca03f-105">Дополнительные сведения о вставке, обновлении и удалении запросов см. в разделе [изменение создания SQL](modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="ca03f-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="ca03f-106">Для усвоения данного раздела требуется знание [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и модели поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ca03f-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="ca03f-107">Также требуется знание деревьев команд и <xref:System.Data.Common.CommandTrees.DbExpression>.</span><span class="sxs-lookup"><span data-stu-id="ca03f-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="ca03f-108">Роль модуля создания кода SQL</span><span class="sxs-lookup"><span data-stu-id="ca03f-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="ca03f-109">Модуль создания кода SQ поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] переводит данное дерево команд запроса в одну инструкцию SQL SELECT, предназначенную для базы данных, которая совместима с SQL:1999.</span><span class="sxs-lookup"><span data-stu-id="ca03f-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="ca03f-110">В созданном коде SQL должно как можно меньше вложенных запросов.</span><span class="sxs-lookup"><span data-stu-id="ca03f-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="ca03f-111">Упрощение дерева команд выходного запроса в модуле создания кода SQL не допускается.</span><span class="sxs-lookup"><span data-stu-id="ca03f-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="ca03f-112">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] может с этой целью, например, удалить соединения и свернуть последовательные узлы фильтра.</span><span class="sxs-lookup"><span data-stu-id="ca03f-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="ca03f-113">Класс <xref:System.Data.Common.DbProviderServices> является начальной точкой для доступа к уровню создания кода SQL для преобразования деревьев команд в <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="ca03f-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca03f-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ca03f-114">In This Section</span></span>  
 [<span data-ttu-id="ca03f-115">Форма деревьев команд</span><span class="sxs-lookup"><span data-stu-id="ca03f-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="ca03f-116">Создание кода SQL из деревьев команд. Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ca03f-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="ca03f-117">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="ca03f-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca03f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ca03f-118">See also</span></span>

- [<span data-ttu-id="ca03f-119">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ca03f-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
