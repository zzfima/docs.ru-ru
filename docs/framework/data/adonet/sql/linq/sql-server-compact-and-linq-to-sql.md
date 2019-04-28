---
title: SQL Server Compact и LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: db3f7aef082d965dc27b69f5a966ff038c0ffac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917856"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="72927-102">SQL Server Compact и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="72927-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="72927-103">SQL Server Compact — это база данных по умолчанию, установленные с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72927-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="72927-104">Дополнительные сведения см. в разделе [с помощью SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="72927-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="72927-105">В этом разделе описаны основные отличия использования, конфигурации, наборы функций и рамки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.</span><span class="sxs-lookup"><span data-stu-id="72927-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="72927-106">Характеристики SQL Server Compact относительно LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="72927-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="72927-107">По умолчанию SQL Server Compact установлена для всех выпусков Visual Studio и поэтому доступна на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72927-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="72927-108">Однако развертывание приложения, использующего SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от поведения для приложения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72927-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="72927-109">SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="72927-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="72927-110">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="72927-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="72927-111">SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).</span><span class="sxs-lookup"><span data-stu-id="72927-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="72927-112">SQL Server Compact выполняется в том же процессе, что и клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="72927-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="72927-113">Эффективность взаимодействия с SQL Server Compact, поэтому может быть значительно выше, чем взаимодействие с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72927-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="72927-114">С другой стороны SQL Server Compact требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.</span><span class="sxs-lookup"><span data-stu-id="72927-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="72927-115">Размер SQL Server Compact библиотеки DLL, мал.</span><span class="sxs-lookup"><span data-stu-id="72927-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="72927-116">Данная функция сокращает общий размер приложения.</span><span class="sxs-lookup"><span data-stu-id="72927-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="72927-117">Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="72927-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="72927-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="72927-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="72927-119">Набор возможностей</span><span class="sxs-lookup"><span data-stu-id="72927-119">Feature Set</span></span>  
 <span data-ttu-id="72927-120">Набор функций SQL Server Compact гораздо проще, чем набор функций SQL Server одним из следующих способов, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложений:</span><span class="sxs-lookup"><span data-stu-id="72927-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="72927-121">SQL Server Compact не поддерживает хранимые процедуры или представления.</span><span class="sxs-lookup"><span data-stu-id="72927-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="72927-122">SQL Server Compact поддерживает только подмножество типов данных и функций SQL.</span><span class="sxs-lookup"><span data-stu-id="72927-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="72927-123">SQL Server Compact поддерживает только подмножество конструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="72927-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="72927-124">SQL Server Compact предоставляет только минимальный оптимизатор.</span><span class="sxs-lookup"><span data-stu-id="72927-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="72927-125">Вполне возможно, что некоторые запросы, время ожидания может истечь.</span><span class="sxs-lookup"><span data-stu-id="72927-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="72927-126">SQL Server Compact не поддерживает частичное доверие.</span><span class="sxs-lookup"><span data-stu-id="72927-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72927-127">См. также</span><span class="sxs-lookup"><span data-stu-id="72927-127">See also</span></span>

- [<span data-ttu-id="72927-128">Ссылки</span><span class="sxs-lookup"><span data-stu-id="72927-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
