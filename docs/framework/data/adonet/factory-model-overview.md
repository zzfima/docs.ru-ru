---
title: "Общие сведения о модели фабрики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0194cd6789ae6ddebeeee65abf1a4fca4a2bc0d6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="factory-model-overview"></a><span data-ttu-id="cbc9f-102">Общие сведения о модели фабрики</span><span class="sxs-lookup"><span data-stu-id="cbc9f-102">Factory Model Overview</span></span>
<span data-ttu-id="cbc9f-103">В ADO.NET 2.0 в пространстве имен <xref:System.Data.Common> появились новые базовые классы.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="cbc9f-104">Эти базовые классы являются абстрактными, что означает, что для них нельзя создавать экземпляры напрямую.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="cbc9f-105">К ним относятся классы <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbDataAdapter>; они совместно используются такими поставщиками данных платформы .NET Framework, как <xref:System.Data.SqlClient> и <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="cbc9f-106">Добавление базовых классов упрощает создание новых функций для поставщиков данных .NET Framework без необходимости в создании новых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="cbc9f-107">В ADO.NET 2.0 также появились абстрактные базовые классы, с помощью которых разработчик может создавать обобщенный код доступа к данным, не зависящий от конкретного поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="cbc9f-108">Фабричный конструктивный шаблон</span><span class="sxs-lookup"><span data-stu-id="cbc9f-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="cbc9f-109">В основе модели программирования для написания не зависящего от поставщиков кода лежит использование «фабричного» конструктивного шаблона, в котором используется один API-интерфейс для доступа к базам данных нескольких поставщиков.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="cbc9f-110">Этому шаблону присваивается соответствующее имя, поскольку он задает использование специализированного объекта, только чтобы создавать другие объекты, что очень напоминает настоящую фабрику.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="cbc9f-111">Более подробное описание фабричного конструктивного шаблона см. в разделе «[написания универсального кода доступа к данным в ASP.NET 2.0 и ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)» и «Универсального кодирования с ADO.NET 2.0 базовых классов и фабрик» [http:// MSDN.Microsoft.com/library/Default.ASP?URL=/Library/dnvs05/HTML/vsgenerics.ASP](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-111">For a more detailed description of the factory design pattern, see "[Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" and "Generic Coding with the ADO.NET 2.0 Base Classes and Factories" [http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) on MSDN.</span></span>  
  
 <span data-ttu-id="cbc9f-112">Начиная с ADO.NET 2.0, для создания экземпляра <xref:System.Data.Common.DbProviderFactories> класс `static` предоставляет методы `Shared` (<xref:System.Data.Common.DbProviderFactory> в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cbc9f-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="cbc9f-113">После этого экземпляр возвращает правильный строго типизированный объект, основанный на данных поставщика и строке соединения, предоставленной во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cbc9f-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc9f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc9f-114">See Also</span></span>  
 [<span data-ttu-id="cbc9f-115">Получение класса DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="cbc9f-115">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="cbc9f-116">DbConnection, DbCommand и DbException</span><span class="sxs-lookup"><span data-stu-id="cbc9f-116">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="cbc9f-117">Изменение данных с помощью DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="cbc9f-117">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="cbc9f-118">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbc9f-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
