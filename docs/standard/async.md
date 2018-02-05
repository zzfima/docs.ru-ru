---
title: "Обзор асинхронной модели"
description: "Сведения о том, что асинхронное программирование — это ключевая методика, которая упрощает обработку блокирующих операций ввода-вывода и параллельных операций на нескольких ядрах."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f2dddc21dfb124fe97c397a156743981a67e4037
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="async-overview"></a><span data-ttu-id="1bd95-104">Обзор асинхронной модели</span><span class="sxs-lookup"><span data-stu-id="1bd95-104">Async Overview</span></span>

<span data-ttu-id="1bd95-105">Не так давно ускорение работы приложений обеспечивалось простой покупкой нового ПК или сервера, однако со временем эта тенденция сошла на нет.</span><span class="sxs-lookup"><span data-stu-id="1bd95-105">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="1bd95-106">Более того, она обернулась вспять.</span><span class="sxs-lookup"><span data-stu-id="1bd95-106">In fact, it reversed.</span></span> <span data-ttu-id="1bd95-107">Появились мобильные телефоны с процессорами ARM с частотой каждого ядра 1 ГГц, а серверные рабочие нагрузки были перенесены в виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="1bd95-107">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="1bd95-108">Пользователи по-прежнему хотят иметь быстрый и отзывчивый интерфейс, а деловые пользователи хотят, чтобы их серверы масштабировались с ростом их бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1bd95-108">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="1bd95-109">Переход на мобильные и облачные решения 3 миллиарда подключенных к Интернету пользователей привели к появлению нового набора шаблонов ПО.</span><span class="sxs-lookup"><span data-stu-id="1bd95-109">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="1bd95-110">Клиентские приложения должны быть постоянно доступны, всегда подключены к сети, мгновенно реагировать на действия пользователей (например, касания экрана) и иметь высокий рейтинг в магазинах приложений.</span><span class="sxs-lookup"><span data-stu-id="1bd95-110">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="1bd95-111">Службы должны справляться со всплесками трафика, корректно выполняя масштабирование вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="1bd95-111">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="1bd95-112">Асинхронное программирование — это ключевая методика, которая упрощает обработку блокирующих операций ввода-вывода и параллельных операций на нескольких ядрах.</span><span class="sxs-lookup"><span data-stu-id="1bd95-112">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="1bd95-113">.NET позволяет приложениям и службам сохранять гибкость и оставаться эластичными благодаря простым моделям асинхронного программирования на уровне языка в C#, VB и F#.</span><span class="sxs-lookup"><span data-stu-id="1bd95-113">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="1bd95-114">Зачем писать асинхронный код?</span><span class="sxs-lookup"><span data-stu-id="1bd95-114">Why Write Async Code?</span></span>

<span data-ttu-id="1bd95-115">Современные приложения активно используют файловые и сетевые операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="1bd95-115">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="1bd95-116">API ввода-вывода обычно являются блокирующими по умолчанию, в результате чего возникают зависания пользовательского интерфейса и снижается эффективность использования оборудования. Избежать этого можно, только научившись пользоваться сложными шаблонами.</span><span class="sxs-lookup"><span data-stu-id="1bd95-116">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="1bd95-117">Основанные на задачах асинхронные интерфейсы API и модель асинхронного программирования на уровне языка меняют эту диспозицию и делают асинхронное выполнение режимом по умолчанию, при этом для их использования требуется освоить совсем немного новых понятий.</span><span class="sxs-lookup"><span data-stu-id="1bd95-117">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="1bd95-118">Асинхронный код имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="1bd95-118">Async code has the following characteristics:</span></span>

* <span data-ttu-id="1bd95-119">Обрабатывает больше запросов сервера, предоставляя потокам возможность обрабатывать больше запросов во время ожидания результата от запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="1bd95-119">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="1bd95-120">Делает пользовательский интерфейс более быстрым, выделяя потоки для обработки действий в пользовательском интерфейсе во время ожидания запросов ввода-вывода и передавая затратные по времени операции другим ядрам ЦП.</span><span class="sxs-lookup"><span data-stu-id="1bd95-120">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="1bd95-121">Многие новые API-интерфейсы .NET являются асинхронными.</span><span class="sxs-lookup"><span data-stu-id="1bd95-121">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="1bd95-122">Писать асинхронный код в .NET очень просто.</span><span class="sxs-lookup"><span data-stu-id="1bd95-122">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="1bd95-123">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="1bd95-123">What's next?</span></span>

<span data-ttu-id="1bd95-124">Основные понятия и методы асинхронного программирования подробно рассматриваются в статьях [Подробный обзор асинхронного программирования](async-in-depth.md) и [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md) (Асинхронное программирование на основе задач).</span><span class="sxs-lookup"><span data-stu-id="1bd95-124">For a deep dive into async concepts and programming, see [Async in depth](async-in-depth.md) and [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>
