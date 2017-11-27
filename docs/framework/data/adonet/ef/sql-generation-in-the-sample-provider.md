---
title: "Создание кода SQL в образце поставщика"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58a49f7bf5d385466810a3c59bda748ef66d5840
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="7b903-102">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="7b903-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="7b903-103">[Образца поставщика Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) демонстрируются новые компоненты поставщиков данных ADO.NET, который поддерживает [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b903-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="7b903-104">Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b903-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="7b903-105">Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="7b903-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b903-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="7b903-106">In This Section</span></span>  
 <span data-ttu-id="7b903-107">Этот раздел содержит следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="7b903-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="7b903-108">Архитектуры и проектирования</span><span class="sxs-lookup"><span data-stu-id="7b903-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="7b903-109">Пошаговое руководство: Создание кода SQL</span><span class="sxs-lookup"><span data-stu-id="7b903-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b903-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7b903-110">See Also</span></span>  
 [<span data-ttu-id="7b903-111">Создание кода SQL</span><span class="sxs-lookup"><span data-stu-id="7b903-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
