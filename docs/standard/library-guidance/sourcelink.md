---
title: SourceLink и библиотеки .NET
description: Практические рекомендации по использованию SourceLink для повышения эффективности отладки для библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: be97f868e2fcfc6c45e4bbac45b033f8914f4d99
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333542"
---
# <a name="sourcelink"></a><span data-ttu-id="021e0-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="021e0-103">SourceLink</span></span>

<span data-ttu-id="021e0-104">SourceLink — это технология, которая дает возможность разработчикам выполнять отладку исходного кода сборок .NET из NuGet.</span><span class="sxs-lookup"><span data-stu-id="021e0-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="021e0-105">SourceLink выполняется при создании пакета NuGet и внедряет метаданные системы управления версиями внутри сборки и пакета.</span><span class="sxs-lookup"><span data-stu-id="021e0-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="021e0-106">Разработчики, загрузившие пакет (функция SourceLink должна быть включена в Visual Studio), могут выполнить исходный код по шагам.</span><span class="sxs-lookup"><span data-stu-id="021e0-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="021e0-107">SourceLink предоставляет метаданные системы управления версиями для создания эффективной среды отладки.</span><span class="sxs-lookup"><span data-stu-id="021e0-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="021e0-108">Демонстрация SourceLink</span><span class="sxs-lookup"><span data-stu-id="021e0-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="021e0-109">Использование SourceLink</span><span class="sxs-lookup"><span data-stu-id="021e0-109">Using SourceLink</span></span>

<span data-ttu-id="021e0-110">Инструкции по использованию SourceLink можно найти в репозитории GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="021e0-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="021e0-111">Вы можете использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), чтобы убедиться, что метаданные SourceLink успешно внедрены в пакет.</span><span class="sxs-lookup"><span data-stu-id="021e0-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="021e0-112">Проверьте наличие метаданных `Repository` с идентификатором комментария и убедитесь, что для каждой DLL-библиотеки целевого пакета есть PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="021e0-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="021e0-113">![SourceLink в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span><span class="sxs-lookup"><span data-stu-id="021e0-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="021e0-114">**✔️ РЕКОМЕНДУЕТСЯ** использовать SourceLink для добавления метаданных системы управления версиями в сборки и пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="021e0-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="021e0-115">Вы можете дополнительно повысить эффективность отладки путем добавления атрибутов отладчика в типы.</span><span class="sxs-lookup"><span data-stu-id="021e0-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="021e0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> может определять, как класс или поле будет отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="021e0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="021e0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> дает отладчику указание о сквозной обработке кода (вместо выполнения по шагам).</span><span class="sxs-lookup"><span data-stu-id="021e0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="021e0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли член отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="021e0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="021e0-119">**✔️ ДОПУСТИМО.** Публикация файлов символов (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="021e0-119">**✔️ CONSIDER** publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="021e0-120">См. дополнительные сведения о [файлах и пакетах символов](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="021e0-120">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="021e0-121">[Назад](dependencies.md)
>[Вперед](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="021e0-121">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
