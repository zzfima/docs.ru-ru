---
title: Создание кода SQL в образце поставщика
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: cba1cec6d7ef0fdf8d4d4cf6c8e44fb325cf6447
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556209"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="fca2d-102">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="fca2d-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="fca2d-103">[Образца поставщика Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fca2d-103">The [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="fca2d-104">Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="fca2d-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="fca2d-105">Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="fca2d-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fca2d-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="fca2d-106">In This Section</span></span>  
 <span data-ttu-id="fca2d-107">Этот раздел содержит следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="fca2d-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="fca2d-108">Архитектура и разработка</span><span class="sxs-lookup"><span data-stu-id="fca2d-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="fca2d-109">Пошаговое руководство. Создание кода SQL</span><span class="sxs-lookup"><span data-stu-id="fca2d-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="fca2d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fca2d-110">See Also</span></span>  
 [<span data-ttu-id="fca2d-111">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="fca2d-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
