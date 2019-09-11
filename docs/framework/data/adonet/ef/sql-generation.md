---
title: Создание SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854354"
---
# <a name="sql-generation"></a><span data-ttu-id="51ede-102">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="51ede-102">SQL Generation</span></span>
<span data-ttu-id="51ede-103">При написании поставщика Entity Framework необходимо преобразовать деревья команд Entity Framework в SQL, которые может распознать конкретная база данных, например Transact-SQL для SQL Server или PL/SQL для Oracle.</span><span class="sxs-lookup"><span data-stu-id="51ede-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="51ede-104">В этом разделе вы узнаете, как разработать компонент создания SQL (для запросов SELECT) для поставщика Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="51ede-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="51ede-105">Дополнительные сведения о вставке, обновлении и удалении запросов см. в разделе [изменение создания SQL](modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="51ede-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="51ede-106">Чтобы понять этот раздел, необходимо ознакомиться с Entity Framework и моделью поставщика ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="51ede-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="51ede-107">Также требуется знание деревьев команд и <xref:System.Data.Common.CommandTrees.DbExpression>.</span><span class="sxs-lookup"><span data-stu-id="51ede-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="51ede-108">Роль модуля создания кода SQL</span><span class="sxs-lookup"><span data-stu-id="51ede-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="51ede-109">Модуль создания SQL поставщика Entity Framework преобразует заданное дерево команд запроса в одну инструкцию SQL SELECT, предназначенную для базы данных SQL: 1999.</span><span class="sxs-lookup"><span data-stu-id="51ede-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="51ede-110">В созданном коде SQL должно как можно меньше вложенных запросов.</span><span class="sxs-lookup"><span data-stu-id="51ede-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="51ede-111">Упрощение дерева команд выходного запроса в модуле создания кода SQL не допускается.</span><span class="sxs-lookup"><span data-stu-id="51ede-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="51ede-112">Entity Framework сделает это, например, исключив объединения и свертывание последовательных узлов фильтров.</span><span class="sxs-lookup"><span data-stu-id="51ede-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="51ede-113">Класс <xref:System.Data.Common.DbProviderServices> является начальной точкой для доступа к уровню создания кода SQL для преобразования деревьев команд в <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="51ede-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51ede-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="51ede-114">In This Section</span></span>  
 [<span data-ttu-id="51ede-115">Форма деревьев команд</span><span class="sxs-lookup"><span data-stu-id="51ede-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="51ede-116">Создание кода SQL из деревьев команд. Рекомендации</span><span class="sxs-lookup"><span data-stu-id="51ede-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="51ede-117">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="51ede-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="51ede-118">См. также</span><span class="sxs-lookup"><span data-stu-id="51ede-118">See also</span></span>

- [<span data-ttu-id="51ede-119">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="51ede-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
