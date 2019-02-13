---
title: Как выполнить  установку сборки в глобальный кэш сборок
ms.date: 02/05/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 233a7803cb59f9bfeac15d293dc3fb5a0db449c9
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903763"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="a6f56-102">Как выполнить  установку сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="a6f56-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="a6f56-103">В глобальном кэше сборок сохраняются сборки, которые могут использоваться несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="a6f56-103">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="a6f56-104">Установите сборку в [глобальный кэш сборок](gac.md) с одним из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="a6f56-104">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span> 
- [<span data-ttu-id="a6f56-105">Установщик Windows</span><span class="sxs-lookup"><span data-stu-id="a6f56-105">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="a6f56-106">Средство глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="a6f56-106">Global assembly cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="a6f56-107">В кэш могут быть установлены только сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="a6f56-107">You can install only strong-named assemblies into the GAC.</span></span> <span data-ttu-id="a6f56-108">Дополнительные сведения о создании сборки со строгим именем см. в разделе [Практическое руководство. Подписание сборки со строгим именем](how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="a6f56-108">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="a6f56-109">Установщик Windows</span><span class="sxs-lookup"><span data-stu-id="a6f56-109">Windows Installer</span></span>

<span data-ttu-id="a6f56-110">[Установщик Windows](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache) — средство установки Windows, которое рекомендуется использовать для добавления сборок в GAC.</span><span class="sxs-lookup"><span data-stu-id="a6f56-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="a6f56-111">Установщик Windows предоставляет возможность подсчета ссылок на сборки в GAC и другие дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="a6f56-111">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="a6f56-112">Создать пакет установщика для установщика Windows можно с помощью [расширения Wix Toolset для Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span><span class="sxs-lookup"><span data-stu-id="a6f56-112">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="a6f56-113">Средство глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="a6f56-113">Global assembly cache tool</span></span>

<span data-ttu-id="a6f56-114">[Средство глобального кэша сборок (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) можно использовать для добавления сборок в глобальный кэш сборок и для просмотра содержимого указанного кэша.</span><span class="sxs-lookup"><span data-stu-id="a6f56-114">You can use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6f56-115">*Gacutil.exe* предназначен только для разработки.</span><span class="sxs-lookup"><span data-stu-id="a6f56-115">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="a6f56-116">Не используйте его для установки рабочих сборок в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a6f56-116">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="a6f56-117">Синтаксис для использования *gacutil.exe* для установки сборки в глобальном кэше сборок выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6f56-117">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```console
gacutil -i <assembly name>
```

<span data-ttu-id="a6f56-118">В этой команде *\<имя сборки>* представляет собой имя сборки, устанавливаемой в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a6f56-118">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="a6f56-119">Если *gacutil.exe* не находится в системном пути, используйте [командную строку разработчика для VS *\<версии>*](../tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a6f56-119">If *gacutil.exe* isn't in your system path, use the [Developer Command Prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="a6f56-120">В следующем примере выполняется установка сборки с именем файла *hello.dll* в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a6f56-120">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```console
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="a6f56-121">В предыдущих версиях .NET Framework расширение оболочки Windows *Shfusion.dll* позволяло устанавливать сборки, перетаскивая их в проводнике.</span><span class="sxs-lookup"><span data-stu-id="a6f56-121">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="a6f56-122">Начиная с версии .NET Framework 4 расширение оболочки *Shfusion.dll* является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="a6f56-122">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f56-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a6f56-123">See also</span></span>

- [<span data-ttu-id="a6f56-124">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="a6f56-124">Working with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="a6f56-125">Практическое руководство. Удаление сборки из глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="a6f56-125">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="a6f56-126">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="a6f56-126">Gacutil.exe (Global assembly cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="a6f56-127">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="a6f56-127">How to: Sign an assembly with a strong name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)
