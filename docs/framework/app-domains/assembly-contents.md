---
title: "Содержимое сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 864e90fea6eb3e65a5a35a9eac38eaecf2299e41
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-contents"></a><span data-ttu-id="8e5f0-102">Содержимое сборок</span><span class="sxs-lookup"><span data-stu-id="8e5f0-102">Assembly Contents</span></span>
<span data-ttu-id="8e5f0-103">В общем случае статическая сборка может состоять из четырех элементов.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="8e5f0-104">[Манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md), который содержит метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="8e5f0-105">Метаданные типов.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="8e5f0-106">Реализующий типы код на промежуточном языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="8e5f0-107">Набор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-107">A set of resources.</span></span>  
  
 <span data-ttu-id="8e5f0-108">Обязательным является лишь манифест сборки, однако остальные типы ресурсов необходимы для обеспечения нужной функциональности сборки.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="8e5f0-109">Существует несколько способов группировки этих элементов в сборку.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="8e5f0-110">Все эти элементы можно объединить в одном физическом файле, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="8e5f0-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="8e5f0-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="8e5f0-112">Сборка из одного файла</span><span class="sxs-lookup"><span data-stu-id="8e5f0-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="8e5f0-113">Или элементы сборки могут находиться в нескольких файлах.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="8e5f0-114">Эти файлы могут быть модулями скомпилированного кода (.netmodule), ресурсами (например, файлами BMP или JPG) или иными файлами, необходимыми приложению.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="8e5f0-115">Сборка из нескольких файлов создается, если необходимо собрать модули, написанные на различных языках, и оптимизировать загрузку приложения, выделяя редко используемые пользовательские типы в модуль, который будет загружаться только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="8e5f0-116">На следующем рисунке разработчик гипотетического приложения выделил в отдельный модуль некоторый вспомогательный код, а ресурс большого объема (BMP-рисунок) оставил в первоначальном файле.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="8e5f0-117">При использовании .NET Framework загрузка файла выполняется только при ссылке; процесс загрузки кода оптимизируется путем размещения в отдельном файле кода, ссылки на который используются редко.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="8e5f0-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="8e5f0-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="8e5f0-119">Сборка из нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="8e5f0-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e5f0-120">Файлы, составляющие такую сборку, не являются физически связанными в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="8e5f0-121">Скорее они связываются друг с другом с помощью манифеста сборки, а среда CLR управляет ими как одним целым.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="8e5f0-122">На этом рисунке все три принадлежащих сборке файла описаны в манифесте сборки, который находится в файле MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="8e5f0-123">Для файловой системы они являются тремя различными файлами.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="8e5f0-124">Обратите внимание: Util.netmodule был скомпилирован как модуль, поскольку он не содержит данных о сборке.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="8e5f0-125">При создании сборки ее манифест был добавлен в файл MyAssembly.dll, чтобы связать сборку с файлами Util.netmodule и Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="8e5f0-126">При проектировании исходного кода необходимо принять определенные решения о способе разделения функций приложения между одним или несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="8e5f0-127">При проектировании кода .NET Framework необходимо принять аналогичные решения о способе разделения функций между одной или несколькими сборками.</span><span class="sxs-lookup"><span data-stu-id="8e5f0-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5f0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5f0-128">See Also</span></span>  
 <span data-ttu-id="8e5f0-129">[Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="8e5f0-129">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md) </span></span>  
 <span data-ttu-id="8e5f0-130">[Манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md) </span><span class="sxs-lookup"><span data-stu-id="8e5f0-130">[Assembly Manifest](../../../docs/framework/app-domains/assembly-manifest.md) </span></span>  
 [<span data-ttu-id="8e5f0-131">Вопросы безопасности сборок</span><span class="sxs-lookup"><span data-stu-id="8e5f0-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)

