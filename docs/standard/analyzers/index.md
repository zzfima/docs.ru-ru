---
title: "Анализаторы на основе Roslyn в .NET"
description: "Сведения об анализаторах на основе Roslyn, которые находят проблемы и предлагают способы их решения."
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="64792-104">Анализаторы на основе Roslyn</span><span class="sxs-lookup"><span data-stu-id="64792-104">The Roslyn based Analyzers</span></span>

<span data-ttu-id="64792-105">Анализаторы на основе Roslyn используют пакет SDK .NET Compiler (API Roslyn) для анализа исходного кода проекта, поиска проблем и их решения.</span><span class="sxs-lookup"><span data-stu-id="64792-105">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="64792-106">Разные анализаторы ищут разные классы проблем, начиная от действий, которые могут привести к ошибкам, и заканчивая проблемам с безопасностью, связанных с совместимостью API.</span><span class="sxs-lookup"><span data-stu-id="64792-106">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="64792-107">Анализаторы на основе Roslyn работают как в интерактивном режиме, так и во время сборки.</span><span class="sxs-lookup"><span data-stu-id="64792-107">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="64792-108">Анализатор предоставляет разные рекомендации при работе в Visual Studio или во время сборки с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="64792-108">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="64792-109">Когда вы редактируете код в Visual Studio, анализаторы выполняются по мере внесения изменений, определяя возможные проблемы, который этот код может вызывать.</span><span class="sxs-lookup"><span data-stu-id="64792-109">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="64792-110">Все проблемы выделяются с помощью волнистой линии.</span><span class="sxs-lookup"><span data-stu-id="64792-110">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="64792-111">В Visual Studio отображается значок лампочки. Когда вы щелкните его, анализатор предложит возможные решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="64792-111">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="64792-112">При создании проекта в Visual Studio или из командной строки исходный код оценивается анализатором, который затем отображает полный список потенциальных проблем.</span><span class="sxs-lookup"><span data-stu-id="64792-112">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="64792-113">На рисунке ниже показан пример.</span><span class="sxs-lookup"><span data-stu-id="64792-113">The following figure shows one example.</span></span>

![Проблемы, о которых сообщает анализатор Framework](./media/framework-analyzers-2.png)

<span data-ttu-id="64792-115">Анализаторы на основе Roslyn сообщают о возможных проблемах как об ошибках, предупреждениях или сообщениях, в зависимости от серьезности проблемы.</span><span class="sxs-lookup"><span data-stu-id="64792-115">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="64792-116">Анализаторы на основе Roslyn устанавливаются в проекте как пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="64792-116">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="64792-117">Настроенные анализаторы, а также параметры для каждого из них, восстанавливаются и выполняются на любом компьютере разработчика для связанного проекта.</span><span class="sxs-lookup"><span data-stu-id="64792-117">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="64792-118">Работа с анализаторами на основе Roslyn отличается от использования библиотек анализа кода, включая старые версии FxCop и средства анализа безопасности.</span><span class="sxs-lookup"><span data-stu-id="64792-118">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="64792-119">Вам не нужно явно запускать анализаторы на основе Roslyn.</span><span class="sxs-lookup"><span data-stu-id="64792-119">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="64792-120">Вам не нужно использовать пункт "Запустить анализ кода" в меню "Анализ" в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="64792-120">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="64792-121">Анализаторы на основе Roslyn выполняются асинхронно, когда вы работаете.</span><span class="sxs-lookup"><span data-stu-id="64792-121">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="64792-122">Дополнительные сведения об анализаторах</span><span class="sxs-lookup"><span data-stu-id="64792-122">More information on specific analyzers</span></span>

<span data-ttu-id="64792-123">Ниже перечислены анализаторы, рассматриваемые в этой статье:</span><span class="sxs-lookup"><span data-stu-id="64792-123">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="64792-124">[Анализатор API](api-analyzer.md): проверяет код на наличие потенциальных угроз совместимости или использует устаревшие API.</span><span class="sxs-lookup"><span data-stu-id="64792-124">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="64792-125">[Анализатор Framework](framework-analyzer.md): проверяет код, обеспечивая его соответствие руководствам по приложениям .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64792-125">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="64792-126">Эти правила включают несколько рекомендаций, связанных с обеспечением безопасности.</span><span class="sxs-lookup"><span data-stu-id="64792-126">These rules include several security-based recommendations.</span></span>
