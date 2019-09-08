---
title: Руководство по программированию
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: c33c7749599de0450a9f969e5802485d154a61e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781253"
---
# <a name="programming-guide"></a><span data-ttu-id="a1b00-102">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="a1b00-102">Programming Guide</span></span>
<span data-ttu-id="a1b00-103">В этом разделе содержатся сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1b00-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="a1b00-104">При использовании Visual Studio можно также использовать реляционный конструктор объектов для выполнения многих из этих задач.</span><span class="sxs-lookup"><span data-stu-id="a1b00-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="a1b00-105">Можно также выполнить поиск по Документация Майкрософт для конкретных проблем, и вы можете принять участие в [форуме LINQ](https://go.microsoft.com/fwlink/?LinkId=76488), где вы сможете обсуждать более сложные темы подробно с экспертами.</span><span class="sxs-lookup"><span data-stu-id="a1b00-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="a1b00-106">Наконец, [LINQ to SQL: запрос к языку .NET для реляционных данных](https://go.microsoft.com/fwlink/?LinkId=93205) , содержащий технические сведения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] о технологии, завершенный с C# Visual Basic и примерами кода.</span><span class="sxs-lookup"><span data-stu-id="a1b00-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1b00-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a1b00-107">In This Section</span></span>  
 [<span data-ttu-id="a1b00-108">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="a1b00-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="a1b00-109">Описывается создание объектной модели.</span><span class="sxs-lookup"><span data-stu-id="a1b00-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="a1b00-110">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="a1b00-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="a1b00-111">Описывается использование объекта <xref:System.Data.Linq.DataContext> в качестве канала передачи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="a1b00-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="a1b00-112">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="a1b00-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="a1b00-113">Описывается, как выполнять запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], с демонстрацией целого ряда примеров.</span><span class="sxs-lookup"><span data-stu-id="a1b00-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="a1b00-114">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="a1b00-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="a1b00-115">Описывается, как изменять данные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a1b00-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="a1b00-116">Поддержка отладки</span><span class="sxs-lookup"><span data-stu-id="a1b00-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="a1b00-117">Описывается поддержка, доступная для отладки проектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1b00-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="a1b00-118">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="a1b00-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="a1b00-119">Включает дополнительные вопросы для более опытных пользователей, такие как разрешение конфликтов параллелизма, создание новых баз данных и многое другое.</span><span class="sxs-lookup"><span data-stu-id="a1b00-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1b00-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a1b00-120">Related Sections</span></span>  
 [<span data-ttu-id="a1b00-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a1b00-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="a1b00-122">Ссылки на разделы, в которых объясняется технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и демонстрируются ее возможности.</span><span class="sxs-lookup"><span data-stu-id="a1b00-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="a1b00-123">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="a1b00-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="a1b00-124">Ссылки на разделы, в которых демонстрируется использование хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="a1b00-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="a1b00-125">Введение в LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a1b00-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="a1b00-126">Содержит ресурсы, помогающие начать изучение LINQ to SQL с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="a1b00-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="a1b00-127">Знакомство с LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1b00-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="a1b00-128">Содержит ресурсы, помогающие начать изучение LINQ to SQL с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a1b00-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
