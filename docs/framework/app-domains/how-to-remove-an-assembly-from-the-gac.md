---
title: Практическое руководство. Удаление сборки из глобального кэша сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a085ff6955f706bcd90f895c42e6405a28d408a
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834042"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="c7dbe-102">Практическое руководство. Удаление сборки из глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="c7dbe-102">How to: Remove an Assembly from the Global Assembly Cache</span></span>

<span data-ttu-id="c7dbe-103">Существует два способа удаления сборки из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-103">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>

- <span data-ttu-id="c7dbe-104">С помощью [средства глобального кэша сборок (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="c7dbe-104">By using the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="c7dbe-105">Этот вариант можно использовать для удаления сборок, помещенных в глобальный кэш сборок во время разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-105">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>

- <span data-ttu-id="c7dbe-106">С помощью [установщика Windows](/windows/desktop/Msi/windows-installer-portal).</span><span class="sxs-lookup"><span data-stu-id="c7dbe-106">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="c7dbe-107">Этот вариант следует использовать для удаления сборок при тестировании пакетов установки и для рабочих систем.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-107">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>

## <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="c7dbe-108">Удаление сборки с помощью Gacutil.exe</span><span class="sxs-lookup"><span data-stu-id="c7dbe-108">Removing an assembly with Gacutil.exe</span></span>

<span data-ttu-id="c7dbe-109">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c7dbe-109">At the command prompt, type the following command:</span></span>

<span data-ttu-id="c7dbe-110">**gacutil –u** \<*имя_сборки*></span><span class="sxs-lookup"><span data-stu-id="c7dbe-110">**gacutil –u** \<*assembly name*></span></span>

<span data-ttu-id="c7dbe-111">В этой команде *имя_сборки* представляет собой имя сборки, удаляемой из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-111">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>

> [!WARNING]
> <span data-ttu-id="c7dbe-112">Не следует использовать Gacutil.exe для удаления сборок в рабочих системах, так как есть вероятность того, что некоторым приложениям эта сборка все еще нужна.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-112">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="c7dbe-113">Вместо этого следует использовать установщик Windows, который ведет счетчик ссылок для каждой сборки, устанавливаемой в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-113">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>

<span data-ttu-id="c7dbe-114">В следующем примере удаляется сборка с именем `hello.dll` из глобального кэша сборок:</span><span class="sxs-lookup"><span data-stu-id="c7dbe-114">The following example removes an assembly named `hello.dll` from the global assembly cache:</span></span>

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="c7dbe-115">Удаление сборки с помощью установщика Windows</span><span class="sxs-lookup"><span data-stu-id="c7dbe-115">Removing an assembly with Windows Installer</span></span>

<span data-ttu-id="c7dbe-116">В разделе **Программы и компоненты** на **панели управления** выберите приложение, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-116">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="c7dbe-117">Если пакет установки разместил сборки в глобальном кэше сборок, установщик Windows удалит их, если они не используются другим приложением.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-117">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>

> [!NOTE]
> <span data-ttu-id="c7dbe-118">Установщик Windows ведет счетчик ссылок для сборок, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-118">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="c7dbe-119">Сборка удаляется из глобального кэша сборок только в том случае, если число ссылок на нее достигает нуля, то есть если она не используется ни одним приложением, установленным с помощью пакета установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-119">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7dbe-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c7dbe-120">See also</span></span>

- [<span data-ttu-id="c7dbe-121">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="c7dbe-121">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="c7dbe-122">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="c7dbe-122">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)
- [<span data-ttu-id="c7dbe-123">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="c7dbe-123">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
