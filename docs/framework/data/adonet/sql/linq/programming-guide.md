---
title: Руководство по программированию
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 542567cf07e86b642a23a879fa6e5476253005b8
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848942"
---
# <a name="programming-guide"></a><span data-ttu-id="d85ff-102">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="d85ff-102">Programming Guide</span></span>
<span data-ttu-id="d85ff-103">В этом разделе содержатся сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d85ff-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="d85ff-104">Если вы используете Visual Studio, вы также можете использовать объект реляционный конструктор для выполнения многих из этих же задач.</span><span class="sxs-lookup"><span data-stu-id="d85ff-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="d85ff-105">Вы также можете искать документы Майкрософт по конкретным вопросам, и вы можете принять участие в [форуме LIN's,](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)где вы можете подробно обсудить более сложные темы с экспертами.</span><span class="sxs-lookup"><span data-stu-id="d85ff-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="d85ff-106">Наконец, [LIN-к S'L: .NET Язык-интегрированный запрос для реляционных данных](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) белой бумаги детали технологии, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в комплекте с Visual Basic и C q код примеры.</span><span class="sxs-lookup"><span data-stu-id="d85ff-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d85ff-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d85ff-107">In This Section</span></span>  
 [<span data-ttu-id="d85ff-108">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="d85ff-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="d85ff-109">Описывается создание объектной модели.</span><span class="sxs-lookup"><span data-stu-id="d85ff-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="d85ff-110">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="d85ff-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="d85ff-111">Описывается использование объекта <xref:System.Data.Linq.DataContext> в качестве канала передачи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="d85ff-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="d85ff-112">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="d85ff-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="d85ff-113">Описывается, как выполнять запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], с демонстрацией целого ряда примеров.</span><span class="sxs-lookup"><span data-stu-id="d85ff-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="d85ff-114">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="d85ff-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="d85ff-115">Описывается, как изменять данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d85ff-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="d85ff-116">Отладка службы поддержки</span><span class="sxs-lookup"><span data-stu-id="d85ff-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="d85ff-117">Описывается поддержка, доступная для отладки проектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d85ff-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="d85ff-118">Справочная информация</span><span class="sxs-lookup"><span data-stu-id="d85ff-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="d85ff-119">Включает дополнительные вопросы для более опытных пользователей, такие как разрешение конфликтов параллелизма, создание новых баз данных и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d85ff-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d85ff-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d85ff-120">Related Sections</span></span>  
 [<span data-ttu-id="d85ff-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d85ff-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="d85ff-122">Ссылки на разделы, в которых объясняется технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и демонстрируются ее возможности.</span><span class="sxs-lookup"><span data-stu-id="d85ff-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="d85ff-123">Сохраненные процедуры</span><span class="sxs-lookup"><span data-stu-id="d85ff-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="d85ff-124">Ссылки на разделы, в которых демонстрируется использование хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="d85ff-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="d85ff-125">Введение в LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d85ff-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="d85ff-126">Предоставляет ресурсы, которые помогут вам начать узнавать о LIN-L с помощью СЗЛ.</span><span class="sxs-lookup"><span data-stu-id="d85ff-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="d85ff-127">Знакомство с LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85ff-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="d85ff-128">Предоставляет ресурсы, которые помогут вам начать узнавать о КОМПАНИИ с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d85ff-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
