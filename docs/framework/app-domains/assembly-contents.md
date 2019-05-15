---
title: Содержимое сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd41051bd770d3579137aa158e70cef41aed49f8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607827"
---
# <a name="assembly-contents"></a><span data-ttu-id="b224c-102">Содержимое сборок</span><span class="sxs-lookup"><span data-stu-id="b224c-102">Assembly Contents</span></span>
<span data-ttu-id="b224c-103">В общем случае статическая сборка может состоять из четырех элементов.</span><span class="sxs-lookup"><span data-stu-id="b224c-103">In general, a static assembly can consist of four elements:</span></span>  
  
- <span data-ttu-id="b224c-104">[Манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md), который содержит метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="b224c-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
- <span data-ttu-id="b224c-105">Метаданные типов.</span><span class="sxs-lookup"><span data-stu-id="b224c-105">Type metadata.</span></span>  
  
- <span data-ttu-id="b224c-106">Реализующий типы код на промежуточном языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="b224c-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
- <span data-ttu-id="b224c-107">Набор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b224c-107">A set of resources.</span></span>  
  
 <span data-ttu-id="b224c-108">Обязательным является лишь манифест сборки, однако остальные типы ресурсов необходимы для обеспечения нужной функциональности сборки.</span><span class="sxs-lookup"><span data-stu-id="b224c-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="b224c-109">Существует несколько способов группировки этих элементов в сборку.</span><span class="sxs-lookup"><span data-stu-id="b224c-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="b224c-110">Все эти элементы можно объединить в одном физическом файле, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="b224c-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 ![Схема, показывающая однофайловую сборку MyAssembly.dll.](./media/assembly-contents/single-file-assembly.gif)  
  
 <span data-ttu-id="b224c-112">Или элементы сборки могут находиться в нескольких файлах.</span><span class="sxs-lookup"><span data-stu-id="b224c-112">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="b224c-113">Эти файлы могут быть модулями скомпилированного кода (.netmodule), ресурсами (например, файлами BMP или JPG) или иными файлами, необходимыми приложению.</span><span class="sxs-lookup"><span data-stu-id="b224c-113">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="b224c-114">Сборка из нескольких файлов создается, если необходимо собрать модули, написанные на различных языках, и оптимизировать загрузку приложения, выделяя редко используемые пользовательские типы в модуль, который будет загружаться только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b224c-114">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="b224c-115">На следующем рисунке разработчик гипотетического приложения выделил в отдельный модуль некоторый вспомогательный код, а ресурс большого объема (BMP-рисунок) оставил в первоначальном файле.</span><span class="sxs-lookup"><span data-stu-id="b224c-115">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="b224c-116">При использовании .NET Framework загрузка файла выполняется только при ссылке; процесс загрузки кода оптимизируется путем размещения в отдельном файле кода, ссылки на который используются редко.</span><span class="sxs-lookup"><span data-stu-id="b224c-116">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 ![Схема, показывающая многофайловую сборку.](./media/assembly-contents/multifile-assembly-diagram.gif) 
  
> [!NOTE]
>  <span data-ttu-id="b224c-118">Файлы, составляющие такую сборку, не являются физически связанными в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="b224c-118">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="b224c-119">Скорее они связываются друг с другом с помощью манифеста сборки, а среда CLR управляет ими как одним целым.</span><span class="sxs-lookup"><span data-stu-id="b224c-119">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="b224c-120">На этом рисунке все три принадлежащих сборке файла описаны в манифесте сборки, который находится в файле MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="b224c-120">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="b224c-121">Для файловой системы они являются тремя различными файлами.</span><span class="sxs-lookup"><span data-stu-id="b224c-121">To the file system, they are three separate files.</span></span> <span data-ttu-id="b224c-122">Обратите внимание: Util.netmodule был скомпилирован как модуль, поскольку он не содержит данных о сборке.</span><span class="sxs-lookup"><span data-stu-id="b224c-122">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="b224c-123">При создании сборки ее манифест был добавлен в файл MyAssembly.dll, чтобы связать сборку с файлами Util.netmodule и Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="b224c-123">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="b224c-124">При проектировании исходного кода необходимо принять определенные решения о способе разделения функций приложения между одним или несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="b224c-124">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="b224c-125">При проектировании кода .NET Framework необходимо принять аналогичные решения о способе разделения функций между одной или несколькими сборками.</span><span class="sxs-lookup"><span data-stu-id="b224c-125">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b224c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b224c-126">See also</span></span>

- [<span data-ttu-id="b224c-127">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="b224c-127">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="b224c-128">Манифест сборки</span><span class="sxs-lookup"><span data-stu-id="b224c-128">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)
- [<span data-ttu-id="b224c-129">Вопросы безопасности сборок</span><span class="sxs-lookup"><span data-stu-id="b224c-129">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
