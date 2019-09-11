---
title: Создание кода SQL в образце поставщика
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854316"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="57960-102">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="57960-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="57960-103">В [Entity Framework примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="57960-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the Entity Framework.</span></span>  <span data-ttu-id="57960-104">Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="57960-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="57960-105">Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="57960-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57960-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="57960-106">In This Section</span></span>  
 <span data-ttu-id="57960-107">Этот раздел содержит следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="57960-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="57960-108">Архитектура и разработка</span><span class="sxs-lookup"><span data-stu-id="57960-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="57960-109">Пошаговое руководство: Создание SQL</span><span class="sxs-lookup"><span data-stu-id="57960-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="57960-110">См. также</span><span class="sxs-lookup"><span data-stu-id="57960-110">See also</span></span>

- [<span data-ttu-id="57960-111">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="57960-111">SQL Generation</span></span>](sql-generation.md)
