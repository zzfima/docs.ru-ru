---
title: SourceLink и библиотеки .NET
description: Практические рекомендации по использованию SourceLink для повышения эффективности отладки для библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128935"
---
# <a name="sourcelink"></a><span data-ttu-id="549af-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="549af-103">SourceLink</span></span>

<span data-ttu-id="549af-104">SourceLink — это технология, которая дает возможность разработчикам выполнять отладку исходного кода сборок .NET из NuGet.</span><span class="sxs-lookup"><span data-stu-id="549af-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="549af-105">SourceLink выполняется при создании пакета NuGet и внедряет метаданные системы управления версиями внутри сборки и пакета.</span><span class="sxs-lookup"><span data-stu-id="549af-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="549af-106">Разработчики, загрузившие пакет (функция SourceLink должна быть включена в Visual Studio), могут выполнить исходный код по шагам.</span><span class="sxs-lookup"><span data-stu-id="549af-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="549af-107">SourceLink предоставляет метаданные системы управления версиями для создания эффективной среды отладки.</span><span class="sxs-lookup"><span data-stu-id="549af-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="549af-108">Демонстрация SourceLink</span><span class="sxs-lookup"><span data-stu-id="549af-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="549af-109">Использование SourceLink</span><span class="sxs-lookup"><span data-stu-id="549af-109">Using SourceLink</span></span>

<span data-ttu-id="549af-110">Инструкции по использованию SourceLink можно найти в репозитории GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="549af-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="549af-111">Вы можете использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), чтобы убедиться, что метаданные SourceLink успешно внедрены в пакет.</span><span class="sxs-lookup"><span data-stu-id="549af-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="549af-112">Проверьте наличие метаданных `Repository` с идентификатором комментария и убедитесь, что для каждой DLL-библиотеки целевого пакета есть PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="549af-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="549af-113">![SourceLink в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="549af-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="549af-114">**✔️ РЕКОМЕНДУЕТСЯ** использовать SourceLink для добавления метаданных системы управления версиями в сборки и пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="549af-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="549af-115">Вы можете дополнительно повысить эффективность отладки путем добавления атрибутов отладчика в типы.</span><span class="sxs-lookup"><span data-stu-id="549af-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="549af-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> может определять, как класс или поле будет отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="549af-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="549af-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> дает отладчику указание о сквозной обработке кода (вместо выполнения по шагам).</span><span class="sxs-lookup"><span data-stu-id="549af-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="549af-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли член отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="549af-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="549af-119">**✔️ РЕКОМЕНДУЕТСЯ** включить файлы символов (`*.pdb`) в пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="549af-119">**✔️ CONSIDER** including symbol files (`*.pdb`) in the NuGet package.</span></span>

> <span data-ttu-id="549af-120">Как правило, файлы символов публикуются в [пакете символов](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="549af-120">Ordinarily, you'd publish symbol files in a [symbol package](./nuget.md#symbol-packages).</span></span> <span data-ttu-id="549af-121">Сейчас самая популярная платформа для пакетов символов не поддерживает формат переносимых файлов символов (`*.pdb`), которые создаются из проектов в стиле SDK, и пакеты символов использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="549af-121">Currently the main public host for symbol packages doesn't support the portable symbol files (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="549af-122">[Назад](dependencies.md)
>[Вперед](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="549af-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>