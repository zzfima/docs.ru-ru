---
title: "SQL Server Compact и LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2717a94228dc1be8da0d84179201747d60c896a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="abaa7-102">SQL Server Compact и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="abaa7-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="abaa7-103">SQL Server Compact — база данных по умолчанию, устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="abaa7-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="abaa7-104">Дополнительные сведения см. в разделе [PAVE по с помощью SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span><span class="sxs-lookup"><span data-stu-id="abaa7-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="abaa7-105">В этом разделе описаны основные отличия в использовании, конфигурации, наборы функций и области [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.</span><span class="sxs-lookup"><span data-stu-id="abaa7-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="abaa7-106">Характеристики SQL Server Compact относительно LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="abaa7-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="abaa7-107">По умолчанию SQL Server Compact устанавливаются для всех [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] выпуски и поэтому доступна на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abaa7-107">By default, SQL Server Compact is installed for all [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="abaa7-108">Однако развертывание приложения, использующего SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="abaa7-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] application.</span></span> <span data-ttu-id="abaa7-109">SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="abaa7-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="abaa7-110">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="abaa7-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="abaa7-111">SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).</span><span class="sxs-lookup"><span data-stu-id="abaa7-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="abaa7-112">SQL Server Compact выполняется в том же процессе, что и клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="abaa7-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="abaa7-113">Эффективность взаимодействия с SQL Server Compact, поэтому может быть значительно выше, чем с [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abaa7-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="abaa7-114">С другой стороны SQL Server Compact требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.</span><span class="sxs-lookup"><span data-stu-id="abaa7-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="abaa7-115">Устанавливается малый размер SQL Server Compact библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="abaa7-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="abaa7-116">Данная возможность сокращает общий размер приложения.</span><span class="sxs-lookup"><span data-stu-id="abaa7-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="abaa7-117">Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="abaa7-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="abaa7-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="abaa7-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="abaa7-119">Набор возможностей</span><span class="sxs-lookup"><span data-stu-id="abaa7-119">Feature Set</span></span>  
 <span data-ttu-id="abaa7-120">Набор компонентов SQL Server Compact гораздо проще, чем набор функциональных возможностей [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] одним из следующих способов, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложений:</span><span class="sxs-lookup"><span data-stu-id="abaa7-120">The SQL Server Compact feature set is much simpler than the feature set of [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="abaa7-121">SQL Server Compact не поддерживает хранимые процедуры или представления.</span><span class="sxs-lookup"><span data-stu-id="abaa7-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="abaa7-122">SQL Server Compact поддерживает только подмножество типов данных и функций SQL.</span><span class="sxs-lookup"><span data-stu-id="abaa7-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="abaa7-123">SQL Server Compact поддерживает только подмножество конструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="abaa7-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="abaa7-124">SQL Server Compact предоставляет только минимальный оптимизатор.</span><span class="sxs-lookup"><span data-stu-id="abaa7-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="abaa7-125">Это возможно, что некоторые запросы, время ожидания может истечь.</span><span class="sxs-lookup"><span data-stu-id="abaa7-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="abaa7-126">SQL Server Compact не поддерживает частичное доверие.</span><span class="sxs-lookup"><span data-stu-id="abaa7-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abaa7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="abaa7-127">See Also</span></span>  
 [<span data-ttu-id="abaa7-128">Ссылки</span><span class="sxs-lookup"><span data-stu-id="abaa7-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
