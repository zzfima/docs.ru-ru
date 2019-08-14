---
title: Общие сведения о средствах диагностики в .NET Core
description: Общие сведения о средствах и методах диагностики приложений .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974152"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="56ac5-103">Общие сведения о средствах диагностики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="56ac5-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="56ac5-104">Программное обеспечение не всегда работает должным образом, но в .NET Core есть средства и API, которые помогут вам быстро и эффективно диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="56ac5-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="56ac5-105">Эта статья поможет вам выбрать нужные средства.</span><span class="sxs-lookup"><span data-stu-id="56ac5-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="56ac5-106">Управляемые отладчики</span><span class="sxs-lookup"><span data-stu-id="56ac5-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="56ac5-107">Управляемые отладчики позволяют взаимодействовать с программой.</span><span class="sxs-lookup"><span data-stu-id="56ac5-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="56ac5-108">Такие операции, как приостановка, инкрементное выполнение, анализ и возобновление, предоставляют сведения о поведении кода.</span><span class="sxs-lookup"><span data-stu-id="56ac5-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="56ac5-109">Отладчик — это самое подходящее средство для диагностики функциональных проблем, которые можно легко воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="56ac5-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="56ac5-110">Ведение журнала и трассировка</span><span class="sxs-lookup"><span data-stu-id="56ac5-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="56ac5-111">Ведение журнала и трассировка — это связанные методы,</span><span class="sxs-lookup"><span data-stu-id="56ac5-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="56ac5-112">предназначенные для инструментирования кода и создания файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="56ac5-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="56ac5-113">В файлах записываются сведения о том, что делает программа.</span><span class="sxs-lookup"><span data-stu-id="56ac5-113">The files record the details of what a program does.</span></span> <span data-ttu-id="56ac5-114">Эти сведения можно использовать для диагностики самых сложных проблем.</span><span class="sxs-lookup"><span data-stu-id="56ac5-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="56ac5-115">В сочетании с метками времени эти методы также используются для выявления проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="56ac5-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="56ac5-116">Модульное тестирование</span><span class="sxs-lookup"><span data-stu-id="56ac5-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="56ac5-117">Модульное тестирование — это ключевой компонент непрерывной интеграции и развертывания высококачественного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="56ac5-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="56ac5-118">Модульные тесты позволяют сразу же узнать о возникшей проблеме.</span><span class="sxs-lookup"><span data-stu-id="56ac5-118">Unit tests are designed to give you an early warning when you break something.</span></span>
