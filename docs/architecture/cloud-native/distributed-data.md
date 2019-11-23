---
title: Распределенные данные
description: Создание архитектуры облачных приложений .NET для Azure | Распределенные данные для собственных облачных приложений
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841813"
---
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="996d2-103">Распределенные данные для облачных приложений</span><span class="sxs-lookup"><span data-stu-id="996d2-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="996d2-104">При создании собственной облачной системы, состоящей из многих независимых микрослужб, способ обработки изменений в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="996d2-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="996d2-105">Традиционные монолитные приложения применяют централизованное хранилище данных, показанное на рис. 5-1.</span><span class="sxs-lookup"><span data-stu-id="996d2-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![Единая монолитная база данных](./media/single-monolithic-database.png)

<span data-ttu-id="996d2-107">**Рис. 5-1**.</span><span class="sxs-lookup"><span data-stu-id="996d2-107">**Figure 5-1**.</span></span> <span data-ttu-id="996d2-108">Единая монолитная база данных</span><span class="sxs-lookup"><span data-stu-id="996d2-108">Single monolithic database</span></span>

<span data-ttu-id="996d2-109">Обратите внимание на предыдущий рисунок, как все компоненты приложения используют одну реляционную базу данных.</span><span class="sxs-lookup"><span data-stu-id="996d2-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="996d2-110">Этот подход дает множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="996d2-110">There are many benefits to this approach.</span></span> <span data-ttu-id="996d2-111">Очень просто запрашивать данные, распределенные по нескольким таблицам, и легко реализовать [транзакции ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) , обеспечивающие согласованность данных.</span><span class="sxs-lookup"><span data-stu-id="996d2-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="996d2-112">Всегда достигается *немедленная согласованность*: либо все обновления данных, либо ни одна из них.</span><span class="sxs-lookup"><span data-stu-id="996d2-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="996d2-113">Облачные системы применяют архитектуру данных, показанную на рисунке 5-2, в которой каждая микрослужба владеет и инкапсулирует собственные данные.</span><span class="sxs-lookup"><span data-stu-id="996d2-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![Несколько баз данных в микрослужбах](./media/data-across-microservices.png)

<span data-ttu-id="996d2-115">**Рис. 5-2**.</span><span class="sxs-lookup"><span data-stu-id="996d2-115">**Figure 5-2**.</span></span> <span data-ttu-id="996d2-116">Несколько баз данных в микрослужбах</span><span class="sxs-lookup"><span data-stu-id="996d2-116">Multiple databases across microservices</span></span>

<span data-ttu-id="996d2-117">Обратите внимание на то, как на предыдущем рисунке каждая микрослужба владеет и инкапсулирует хранилище данных и предоставляет доступ к данным только внешнему миру из открытого API.</span><span class="sxs-lookup"><span data-stu-id="996d2-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="996d2-118">Эта модель позволяет каждой микрослужбе развиваться независимо без необходимости координировать изменения схемы данных с помощью других микрослужб.</span><span class="sxs-lookup"><span data-stu-id="996d2-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="996d2-119">Каждая микрослужба может реализовать тип хранилища данных (реляционной базы данных, базы данных документов, хранилища ключей и значений), который наилучшим образом соответствует потребностям.</span><span class="sxs-lookup"><span data-stu-id="996d2-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="996d2-120">Во время выполнения каждая микрослужба может соответствующим образом масштабировать свои данные.</span><span class="sxs-lookup"><span data-stu-id="996d2-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="996d2-121">Это показано на рисунке 5-3.</span><span class="sxs-lookup"><span data-stu-id="996d2-121">This is shown in Figure 5-3:</span></span>

![Сохраняемость данных Polyglot](./media/polyglot-data-persistence.png)

<span data-ttu-id="996d2-123">**Рис. 5-3**.</span><span class="sxs-lookup"><span data-stu-id="996d2-123">**Figure 5-3**.</span></span> <span data-ttu-id="996d2-124">Сохраняемость данных Polyglot</span><span class="sxs-lookup"><span data-stu-id="996d2-124">Polyglot data persistence</span></span>

<span data-ttu-id="996d2-125">Обратите внимание, как на предыдущем рисунке Каталог продуктов и микрослужбы инвентаризации применяют реляционные базы данных, микрослужбу заказов, базу данных документов NoSql и микрослужбу корзины покупок, которая является внешним хранилищем "ключ — значение".</span><span class="sxs-lookup"><span data-stu-id="996d2-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="996d2-126">В то время как реляционные базы данных остаются актуальными для микрослужб со сложными данными, базы данных NoSQL получили значительный популярность, обеспечивая адаптируемость, быстрый поиск и высокий уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="996d2-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="996d2-127">Их природа без схем позволяет разработчикам переходить от архитектуры типизированных классов данных и моделей ORM, которые делают изменения затратными и ресурсоемкими.</span><span class="sxs-lookup"><span data-stu-id="996d2-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="996d2-128">[Назад](service-mesh-communication-infrastructure.md)
>[Вперед](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="996d2-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
