---
title: Обзор асинхронной модели
description: Сведения о том, что асинхронное программирование — это ключевая методика, которая упрощает обработку блокирующих операций ввода-вывода и параллельных операций на нескольких ядрах.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: d649bc3a92d3bb834b3bc4f7d3c1bcb0f9417375
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159732"
---
# <a name="async-overview"></a><span data-ttu-id="209e8-103">Обзор асинхронной модели</span><span class="sxs-lookup"><span data-stu-id="209e8-103">Async Overview</span></span>

<span data-ttu-id="209e8-104">Не так давно ускорение работы приложений обеспечивалось простой покупкой нового ПК или сервера, однако со временем эта тенденция сошла на нет.</span><span class="sxs-lookup"><span data-stu-id="209e8-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="209e8-105">Более того, она обернулась вспять.</span><span class="sxs-lookup"><span data-stu-id="209e8-105">In fact, it reversed.</span></span> <span data-ttu-id="209e8-106">Появились мобильные телефоны с процессорами ARM с частотой каждого ядра 1 ГГц, а серверные рабочие нагрузки были перенесены в виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="209e8-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="209e8-107">Пользователи по-прежнему хотят иметь быстрый и отзывчивый интерфейс, а деловые пользователи хотят, чтобы их серверы масштабировались с ростом их бизнеса.</span><span class="sxs-lookup"><span data-stu-id="209e8-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="209e8-108">Переход на мобильные и облачные решения 3 миллиарда подключенных к Интернету пользователей привели к появлению нового набора шаблонов ПО.</span><span class="sxs-lookup"><span data-stu-id="209e8-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span>

- <span data-ttu-id="209e8-109">Клиентские приложения должны быть постоянно доступны, всегда подключены к сети, мгновенно реагировать на действия пользователей (например, касания экрана) и иметь высокий рейтинг в магазинах приложений.</span><span class="sxs-lookup"><span data-stu-id="209e8-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
- <span data-ttu-id="209e8-110">Службы должны справляться со всплесками трафика, корректно выполняя масштабирование вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="209e8-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span>

<span data-ttu-id="209e8-111">Асинхронное программирование — это ключевая методика, которая упрощает обработку блокирующих операций ввода-вывода и параллельных операций на нескольких ядрах.</span><span class="sxs-lookup"><span data-stu-id="209e8-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="209e8-112">.NET позволяет приложениям и службам сохранять гибкость и оставаться эластичными благодаря простым моделям асинхронного программирования на уровне языка в C#, Visual Basic и F#.</span><span class="sxs-lookup"><span data-stu-id="209e8-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, Visual Basic, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="209e8-113">Зачем писать асинхронный код?</span><span class="sxs-lookup"><span data-stu-id="209e8-113">Why Write Async Code?</span></span>

<span data-ttu-id="209e8-114">Современные приложения активно используют файловые и сетевые операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="209e8-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="209e8-115">API ввода-вывода обычно являются блокирующими по умолчанию, в результате чего возникают зависания пользовательского интерфейса и снижается эффективность использования оборудования. Избежать этого можно, только научившись пользоваться сложными шаблонами.</span><span class="sxs-lookup"><span data-stu-id="209e8-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="209e8-116">Основанные на задачах асинхронные интерфейсы API и модель асинхронного программирования на уровне языка меняют эту диспозицию и делают асинхронное выполнение режимом по умолчанию, при этом для их использования требуется освоить совсем немного новых понятий.</span><span class="sxs-lookup"><span data-stu-id="209e8-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="209e8-117">Асинхронный код имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="209e8-117">Async code has the following characteristics:</span></span>

- <span data-ttu-id="209e8-118">Обрабатывает больше запросов сервера, предоставляя потокам возможность обрабатывать больше запросов во время ожидания результата от запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="209e8-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
- <span data-ttu-id="209e8-119">Делает пользовательский интерфейс более быстрым, выделяя потоки для обработки действий в пользовательском интерфейсе во время ожидания запросов ввода-вывода и передавая затратные по времени операции другим ядрам ЦП.</span><span class="sxs-lookup"><span data-stu-id="209e8-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
- <span data-ttu-id="209e8-120">Многие новые API-интерфейсы .NET являются асинхронными.</span><span class="sxs-lookup"><span data-stu-id="209e8-120">Many of the newer .NET APIs are asynchronous.</span></span>
- <span data-ttu-id="209e8-121">Писать асинхронный код в .NET очень просто.</span><span class="sxs-lookup"><span data-stu-id="209e8-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="209e8-122">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="209e8-122">What's next?</span></span>

<span data-ttu-id="209e8-123">Дополнительные сведения см. в статье [Подробный обзор асинхронного программирования](async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="209e8-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="209e8-124">Статья [Шаблоны асинхронного программирования](asynchronous-programming-patterns/index.md) содержит общие сведения о трех шаблонах асинхронного программирования, поддерживаемых в .NET:</span><span class="sxs-lookup"><span data-stu-id="209e8-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="209e8-125">[Асинхронная модель программирования (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (устаревший)</span><span class="sxs-lookup"><span data-stu-id="209e8-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="209e8-126">[Асинхронная модель на основе событий (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (устаревший)</span><span class="sxs-lookup"><span data-stu-id="209e8-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="209e8-127">[Асинхронный шаблон, основанный на задачах (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (рекомендуется для новых разработок)</span><span class="sxs-lookup"><span data-stu-id="209e8-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="209e8-128">Дополнительные сведения о рекомендованных моделях программирования на основе задач см. в статье [Асинхронное программирование на основе задач](parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="209e8-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
