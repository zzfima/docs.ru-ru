---
title: Установка сборки в глобальный кэш сборок
ms.date: 09/20/2018
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
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584585"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="35032-102">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="35032-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="35032-103">Существует два способа установки сборки со строгим именем в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="35032-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35032-104">В кэш могут быть установлены только сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="35032-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="35032-105">Сведения о создании сборки со строгим именем см. в разделе [Практическое руководство. Подписание сборки строгим именем](how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="35032-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="35032-106">Установщик Windows</span><span class="sxs-lookup"><span data-stu-id="35032-106">Windows Installer</span></span>

<span data-ttu-id="35032-107">[Установщик Windows](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache) — средство установки Windows, которое рекомендуется использовать для добавления сборок в GAC.</span><span class="sxs-lookup"><span data-stu-id="35032-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="35032-108">Установщик Windows предоставляет возможность подсчета ссылок на сборки в GAC и другие дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="35032-108">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="35032-109">Создать пакет установщика для установщика Windows можно с помощью [расширения Wix Toolset для Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span><span class="sxs-lookup"><span data-stu-id="35032-109">You can use the [WiX Toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) to create an installer package for Windows Installer.</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="35032-110">Средство глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="35032-110">Global assembly cache tool</span></span>

<span data-ttu-id="35032-111">[Средство глобального кэша сборок (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) можно использовать для добавления сборок со строгими именами в глобальный кэш сборок и для просмотра содержимого указанного кэша.</span><span class="sxs-lookup"><span data-stu-id="35032-111">You can use the [Global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="35032-112">Программа Gacutil.exe предназначена только для использования в процессе разработки и не должна использоваться для установки рабочих сборок в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="35032-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="35032-113">Средство gacutil имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="35032-113">The syntax for gacutil is as follows:</span></span>

```shell
gacutil -i <assembly name>
```

<span data-ttu-id="35032-114">В этой команде *имя сборки* представляет собой имя сборки, устанавливаемой в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="35032-114">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="35032-115">В следующем примере выполняется установка сборки с именем файла `hello.dll` в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="35032-115">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>

```shell
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="35032-116">В предыдущих версиях .NET Framework расширение оболочки Windows Shfusion.dll позволяло устанавливать сборки, перетаскивая их в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="35032-116">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**.</span></span> <span data-ttu-id="35032-117">Начиная с версии .NET Framework 4, расширение оболочки Shfusion.dll является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="35032-117">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="35032-118">См. также</span><span class="sxs-lookup"><span data-stu-id="35032-118">See also</span></span>

- [<span data-ttu-id="35032-119">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="35032-119">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="35032-120">Практическое руководство. Удаление сборки из глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="35032-120">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="35032-121">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="35032-121">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="35032-122">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="35032-122">How to: Sign an Assembly with a Strong Name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)