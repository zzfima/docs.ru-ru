---
title: Общие сведения о средствах диагностики в .NET Core
description: Общие сведения о средствах и методах диагностики приложений .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.topic: overview
ms.openlocfilehash: c0a45a1bfe866ad42890db576b5dd5098b1dbc3d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318345"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="33e47-103">Общие сведения о средствах диагностики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="33e47-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="33e47-104">Программное обеспечение не всегда работает должным образом, но в .NET Core есть средства и API, которые помогут вам быстро и эффективно диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="33e47-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="33e47-105">Эта статья поможет вам выбрать нужные средства.</span><span class="sxs-lookup"><span data-stu-id="33e47-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="33e47-106">Управляемые отладчики</span><span class="sxs-lookup"><span data-stu-id="33e47-106">Managed debuggers</span></span>

<span data-ttu-id="33e47-107">[Управляемые отладчики](managed-debuggers.md) позволяют взаимодействовать с программой.</span><span class="sxs-lookup"><span data-stu-id="33e47-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="33e47-108">Такие операции, как приостановка, инкрементное выполнение, анализ и возобновление, предоставляют сведения о поведении кода.</span><span class="sxs-lookup"><span data-stu-id="33e47-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="33e47-109">Отладчик — это самое подходящее средство для диагностики функциональных проблем, которые можно легко воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="33e47-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="33e47-110">Ведение журнала и трассировка</span><span class="sxs-lookup"><span data-stu-id="33e47-110">Logging and tracing</span></span>

<span data-ttu-id="33e47-111">[Ведение журнала и трассировка](logging-tracing.md) — это связанные методы,</span><span class="sxs-lookup"><span data-stu-id="33e47-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="33e47-112">предназначенные для инструментирования кода и создания файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="33e47-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="33e47-113">В файлах записываются сведения о том, что делает программа.</span><span class="sxs-lookup"><span data-stu-id="33e47-113">The files record the details of what a program does.</span></span> <span data-ttu-id="33e47-114">Эти сведения можно использовать для диагностики самых сложных проблем.</span><span class="sxs-lookup"><span data-stu-id="33e47-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="33e47-115">В сочетании с метками времени эти методы также используются для выявления проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="33e47-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="33e47-116">Модульное тестирование</span><span class="sxs-lookup"><span data-stu-id="33e47-116">Unit testing</span></span>

<span data-ttu-id="33e47-117">[Модульное тестирование](../testing/index.md) — это ключевой компонент непрерывной интеграции и развертывания высококачественного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="33e47-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="33e47-118">Модульные тесты позволяют сразу же узнать о возникшей проблеме.</span><span class="sxs-lookup"><span data-stu-id="33e47-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="33e47-119">Глобальные средства диагностики dotnet в .NET Core</span><span class="sxs-lookup"><span data-stu-id="33e47-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="33e47-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="33e47-120">dotnet-counters</span></span>

<span data-ttu-id="33e47-121">[dotnet-counters](dotnet-counters.md) — это средство мониторинга производительности для первого уровня мониторинга работоспособности и анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="33e47-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="33e47-122">Оно отслеживает значения счетчиков производительности, опубликованные с помощью API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="33e47-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="33e47-123">Например, можно быстро отслеживать использование ЦП или частоту возникновения исключений в приложении .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33e47-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="33e47-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="33e47-124">dotnet-dump</span></span>

<span data-ttu-id="33e47-125">[dotnet-dump](dotnet-dump.md) — это средство сбора и анализа дампов ядра Windows и Linux без собственного отладчика.</span><span class="sxs-lookup"><span data-stu-id="33e47-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="33e47-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="33e47-126">dotnet-trace</span></span>

<span data-ttu-id="33e47-127">.NET Core включает в себя `EventPipe`, с помощью которого предоставляются диагностические данные.</span><span class="sxs-lookup"><span data-stu-id="33e47-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="33e47-128">Средство [dotnet-trace](dotnet-trace.md) позволяет использовать интересные данные профилирования из приложения, которые могут помочь в сценариях, когда вам нужно найти причину медленной работы приложений.</span><span class="sxs-lookup"><span data-stu-id="33e47-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>
