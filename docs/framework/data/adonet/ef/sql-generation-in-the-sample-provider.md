---
title: Создание кода SQL в образце поставщика
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 5aa6e31cfc93a4ae1871da63f466864b4ea6f5d9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149722"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="b3b17-102">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="b3b17-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="b3b17-103">[Образца поставщика Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3b17-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="b3b17-104">Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="b3b17-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="b3b17-105">Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="b3b17-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3b17-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="b3b17-106">In This Section</span></span>  
 <span data-ttu-id="b3b17-107">Этот раздел содержит следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="b3b17-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="b3b17-108">Архитектура и разработка</span><span class="sxs-lookup"><span data-stu-id="b3b17-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="b3b17-109">Пошаговое руководство. Создание кода SQL</span><span class="sxs-lookup"><span data-stu-id="b3b17-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3b17-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b3b17-110">See Also</span></span>  
 [<span data-ttu-id="b3b17-111">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="b3b17-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
