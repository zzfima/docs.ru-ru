---
title: "Руководство по программированию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 03d4febc7e61425d0057c48949b18281ca3dec4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="programming-guide"></a><span data-ttu-id="4220e-102">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="4220e-102">Programming Guide</span></span>
<span data-ttu-id="4220e-103">В этом разделе содержатся сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4220e-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="4220e-104">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут также воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для выполнения многих из этих задач.</span><span class="sxs-lookup"><span data-stu-id="4220e-104">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="4220e-105">Документы Microsoft можно также искать конкретные проблемы, и вы можете принять участие в [форуме по LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), где можно обсудить со специалистами более сложные вопросы подробно.</span><span class="sxs-lookup"><span data-stu-id="4220e-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="4220e-106">Наконец, в техническом документе [LINQ to SQL: запросы LINQ .NET для реляционных данных](http://go.microsoft.com/fwlink/?LinkId=93205) подробно описывается технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и приводятся примеры кода на языках [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C#.</span><span class="sxs-lookup"><span data-stu-id="4220e-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4220e-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="4220e-107">In This Section</span></span>  
 [<span data-ttu-id="4220e-108">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="4220e-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="4220e-109">Описывается создание объектной модели.</span><span class="sxs-lookup"><span data-stu-id="4220e-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="4220e-110">Взаимодействие с базой данных</span><span class="sxs-lookup"><span data-stu-id="4220e-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="4220e-111">Описывается использование объекта <xref:System.Data.Linq.DataContext> в качестве канала передачи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4220e-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="4220e-112">Запросы к базе данных</span><span class="sxs-lookup"><span data-stu-id="4220e-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="4220e-113">Описывается, как выполнять запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], с демонстрацией целого ряда примеров.</span><span class="sxs-lookup"><span data-stu-id="4220e-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="4220e-114">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="4220e-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="4220e-115">Описывается, как изменять данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4220e-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="4220e-116">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="4220e-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="4220e-117">Описывается поддержка, доступная для отладки проектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4220e-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="4220e-118">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="4220e-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="4220e-119">Включает дополнительные вопросы для более опытных пользователей, такие как разрешение конфликтов параллелизма, создание новых баз данных и многое другое.</span><span class="sxs-lookup"><span data-stu-id="4220e-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4220e-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4220e-120">Related Sections</span></span>  
 [<span data-ttu-id="4220e-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4220e-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="4220e-122">Ссылки на разделы, в которых объясняется технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и демонстрируются ее возможности.</span><span class="sxs-lookup"><span data-stu-id="4220e-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="4220e-123">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="4220e-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="4220e-124">Ссылки на разделы, в которых демонстрируется использование хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="4220e-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="4220e-125">Введение в LINQ</span><span class="sxs-lookup"><span data-stu-id="4220e-125">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 <span data-ttu-id="4220e-126">Содержатся ресурсы, которые могут быть полезными для тех, кто приступает к изучению технологии [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4220e-126">Provides resources to help you begin to learn about [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
