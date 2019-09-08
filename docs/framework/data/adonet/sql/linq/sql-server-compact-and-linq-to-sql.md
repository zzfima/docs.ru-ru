---
title: SQL Server Compact и LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792535"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="43c3e-102">SQL Server Compact и LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="43c3e-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="43c3e-103">SQL Server Compact — это база данных по умолчанию, устанавливаемая вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43c3e-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="43c3e-104">Дополнительные сведения см. [в разделе использование SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="43c3e-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="43c3e-105">В этом разделе описываются основные различия в использовании, конфигурации, наборах функций и области [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.</span><span class="sxs-lookup"><span data-stu-id="43c3e-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="43c3e-106">Характеристики SQL Server Compact относительно LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="43c3e-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="43c3e-107">По умолчанию SQL Server Compact устанавливается для всех выпусков Visual Studio и, следовательно, доступен на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43c3e-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="43c3e-108">Но развертывание приложения, которое использует SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от этого для SQL Server приложения.</span><span class="sxs-lookup"><span data-stu-id="43c3e-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="43c3e-109">SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43c3e-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="43c3e-110">Обратите внимание на следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="43c3e-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="43c3e-111">SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).</span><span class="sxs-lookup"><span data-stu-id="43c3e-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="43c3e-112">SQL Server Compact выполняется в том же процессе, что и клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="43c3e-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="43c3e-113">Таким образом, эффективность взаимодействия с SQL Server Compact может быть значительно выше, чем связь с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43c3e-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="43c3e-114">С другой стороны, SQL Server Compact требует взаимодействия между управляемым и неуправляемым кодом с затратами на его посещение.</span><span class="sxs-lookup"><span data-stu-id="43c3e-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="43c3e-115">Размер SQL Server Compact DLL невелик.</span><span class="sxs-lookup"><span data-stu-id="43c3e-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="43c3e-116">Данная функция сокращает общий размер приложения.</span><span class="sxs-lookup"><span data-stu-id="43c3e-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="43c3e-117">Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="43c3e-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="43c3e-118">Реляционный конструктор объектов не поддерживает SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="43c3e-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="43c3e-119">Набор возможностей</span><span class="sxs-lookup"><span data-stu-id="43c3e-119">Feature Set</span></span>  
 <span data-ttu-id="43c3e-120">Набор функций SQL Server Compact намного проще, чем набор функций SQL Server следующими способами, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложения:</span><span class="sxs-lookup"><span data-stu-id="43c3e-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="43c3e-121">SQL Server Compact не поддерживает хранимые процедуры или представления.</span><span class="sxs-lookup"><span data-stu-id="43c3e-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="43c3e-122">SQL Server Compact поддерживает только подмножество типов данных и функций SQL.</span><span class="sxs-lookup"><span data-stu-id="43c3e-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="43c3e-123">SQL Server Compact поддерживает только подмножество конструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="43c3e-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="43c3e-124">SQL Server Compact предоставляет только минимальный оптимизатор.</span><span class="sxs-lookup"><span data-stu-id="43c3e-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="43c3e-125">Возможно, время ожидания некоторых запросов истекает.</span><span class="sxs-lookup"><span data-stu-id="43c3e-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="43c3e-126">SQL Server Compact не поддерживает частичное доверие.</span><span class="sxs-lookup"><span data-stu-id="43c3e-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c3e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="43c3e-127">See also</span></span>

- [<span data-ttu-id="43c3e-128">Ссылки</span><span class="sxs-lookup"><span data-stu-id="43c3e-128">Reference</span></span>](reference.md)
