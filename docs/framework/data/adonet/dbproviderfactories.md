---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: e3ea9e3d083314f8df25f9edadbd1a18f1227293
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784105"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="c5def-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="c5def-102">DbProviderFactories</span></span>
<span data-ttu-id="c5def-103">Пространство имен <xref:System.Data.Common> предоставляет классы для создания экземпляров <xref:System.Data.Common.DbProviderFactory> для работы с конкретными источниками данных.</span><span class="sxs-lookup"><span data-stu-id="c5def-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="c5def-104">При создании экземпляра <xref:System.Data.Common.DbProviderFactory> и передаче ему сведений о поставщике данных фабрика `DbProviderFactory` может на их основе определить верный, строго типизированный объект соединения, который необходимо возвратить.</span><span class="sxs-lookup"><span data-stu-id="c5def-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="c5def-105">Начиная с версии 4 платформы .NET Framework, такие поставщики данных, как <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> и <xref:System.Data.OracleClient>, больше не перечисляются в файле machine.config, однако настраиваемые поставщики будут по-прежнему перечислены там.</span><span class="sxs-lookup"><span data-stu-id="c5def-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5def-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c5def-106">In This Section</span></span>  
 [<span data-ttu-id="c5def-107">Общие сведения о модели фабрики</span><span class="sxs-lookup"><span data-stu-id="c5def-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="c5def-108">Содержит общие сведения о шаблоне разработки и программном интерфейсе фабрики.</span><span class="sxs-lookup"><span data-stu-id="c5def-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="c5def-109">Получение класса DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="c5def-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="c5def-110">Показывает способ создания списка установленных поставщиков данных и соединения <xref:System.Data.Common.DbConnection> в фабрике `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="c5def-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="c5def-111">DbConnection, DbCommand и DbException</span><span class="sxs-lookup"><span data-stu-id="c5def-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="c5def-112">Показывает способ создания объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbDataReader>, а также методы обработки ошибок с помощью исключения <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="c5def-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="c5def-113">Изменение данных с помощью DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="c5def-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="c5def-114">Показывает способ использования объектов <xref:System.Data.Common.DbCommandBuilder> совместно с <xref:System.Data.Common.DbDataAdapter> для получения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="c5def-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5def-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c5def-115">See also</span></span>

- [<span data-ttu-id="c5def-116">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5def-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c5def-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5def-117">ADO.NET Overview</span></span>](ado-net-overview.md)
