---
title: Библиотеки SourceLink и .NET
description: Практические рекомендации по использованию SourceLink для улучшения отладки для библиотеки .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370317"
---
# <a name="sourcelink"></a><span data-ttu-id="77560-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="77560-103">SourceLink</span></span>

<span data-ttu-id="77560-104">SourceLink — это технология, которая разрешает отладку исходного кода сборок .NET из NuGet разработчиками.</span><span class="sxs-lookup"><span data-stu-id="77560-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="77560-105">SourceLink выполняет при создании пакета NuGet и внедряет источника метаданных элемента управления внутри сборки и пакет.</span><span class="sxs-lookup"><span data-stu-id="77560-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="77560-106">Разработчики, загрузившие пакета и иметь SourceLink включена в Visual Studio можно зайти в его исходный код.</span><span class="sxs-lookup"><span data-stu-id="77560-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="77560-107">SourceLink предоставляет источник метаданных элемента управления для создания удобной отладки.</span><span class="sxs-lookup"><span data-stu-id="77560-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="77560-108">Демонстрация SourceLink</span><span class="sxs-lookup"><span data-stu-id="77560-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="77560-109">С помощью SourceLink</span><span class="sxs-lookup"><span data-stu-id="77560-109">Using SourceLink</span></span>

<span data-ttu-id="77560-110">Инструкции по использованию SourceLink можно найти на [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) репозитория GitHub.</span><span class="sxs-lookup"><span data-stu-id="77560-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="77560-111">Можно использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) для подтверждения того, что метаданные SourceLink успешно внедрен в пакете.</span><span class="sxs-lookup"><span data-stu-id="77560-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="77560-112">Проверьте `Repository` присутствует метаданных с идентификатором комментарий и PDB-файлы находятся с DLL каждый целевой объект.</span><span class="sxs-lookup"><span data-stu-id="77560-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="77560-113">![SourceLink в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink в обозревателе пакетов NuGet")</span><span class="sxs-lookup"><span data-stu-id="77560-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="77560-114">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** Добавление метаданных элемента управления источника сборки и пакет NuGet с помощью SourceLink.</span><span class="sxs-lookup"><span data-stu-id="77560-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

<span data-ttu-id="77560-115">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** включая PDB-файлы в пакете NuGet.</span><span class="sxs-lookup"><span data-stu-id="77560-115">**✔️ CONSIDER** including PDB files in the NuGet package.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="77560-116">[Назад](./dependencies.md)
[Вперед](./publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="77560-116">[Previous](./dependencies.md)
[Next](./publish-nuget-package.md)</span></span>
