---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208820"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="b9d5f-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="b9d5f-102">DbProviderFactories</span></span>
<span data-ttu-id="b9d5f-103">Пространство имен <xref:System.Data.Common> предоставляет классы для создания экземпляров <xref:System.Data.Common.DbProviderFactory> для работы с конкретными источниками данных.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="b9d5f-104">При создании экземпляра <xref:System.Data.Common.DbProviderFactory> и передаче ему сведений о поставщике данных фабрика `DbProviderFactory` может на их основе определить верный, строго типизированный объект соединения, который необходимо возвратить.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="b9d5f-105">Начиная с версии 4 платформы .NET Framework, такие поставщики данных, как <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> и <xref:System.Data.OracleClient>, больше не перечисляются в файле machine.config, однако настраиваемые поставщики будут по-прежнему перечислены там.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9d5f-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b9d5f-106">In This Section</span></span>  
 [<span data-ttu-id="b9d5f-107">Общие сведения о модели фабрики</span><span class="sxs-lookup"><span data-stu-id="b9d5f-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="b9d5f-108">Содержит общие сведения о шаблоне разработки и программном интерфейсе фабрики.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="b9d5f-109">Получение класса DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="b9d5f-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="b9d5f-110">Показывает способ создания списка установленных поставщиков данных и соединения <xref:System.Data.Common.DbConnection> в фабрике `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="b9d5f-111">DbConnection, DbCommand и DbException</span><span class="sxs-lookup"><span data-stu-id="b9d5f-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="b9d5f-112">Показывает способ создания объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbDataReader>, а также методы обработки ошибок с помощью исключения <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="b9d5f-113">Изменение данных с помощью DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="b9d5f-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="b9d5f-114">Показывает способ использования объектов <xref:System.Data.Common.DbCommandBuilder> совместно с <xref:System.Data.Common.DbDataAdapter> для получения и изменения данных.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d5f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b9d5f-115">See also</span></span>

- [<span data-ttu-id="b9d5f-116">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9d5f-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="b9d5f-117">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="b9d5f-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
