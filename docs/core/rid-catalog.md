---
title: Каталог идентификаторов сред выполнения (RID) в .NET Core
description: Сведения об идентификаторах сред выполнения и их использовании в .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.openlocfilehash: 81f9e5f65385bbd81c7fdae7f75c62d11b6f6319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215913"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="a78b1-103">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="a78b1-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="a78b1-104">RID — это сокращение от *Runtime IDentifier* (идентификатор среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="a78b1-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="a78b1-105">Идентификаторы RID служат для идентификации целевых платформ, на которых выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="a78b1-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="a78b1-106">Они используются пакетами .NET для представления ресурсов, специфичных для платформы, в пакетах NuGet.</span><span class="sxs-lookup"><span data-stu-id="a78b1-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="a78b1-107">Некоторые примеры идентификаторов RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` или `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="a78b1-108">Для пакетов с собственными зависимостями они указывают, на каких платформах можно восстановить пакет.</span><span class="sxs-lookup"><span data-stu-id="a78b1-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="a78b1-109">Один идентификатор RID можно задать в элементе `<RuntimeIdentifier>` вашего файла проекта.</span><span class="sxs-lookup"><span data-stu-id="a78b1-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="a78b1-110">Несколько идентификаторов RID можно определить в виде списка, разделенного точкой с запятой, в элементе `<RuntimeIdentifiers>` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="a78b1-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="a78b1-111">Они также используются с помощью параметра `--runtime` со следующими [командами интерфейса командной строки .NET Core](./tools/index.md):</span><span class="sxs-lookup"><span data-stu-id="a78b1-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="a78b1-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="a78b1-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="a78b1-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a78b1-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="a78b1-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a78b1-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="a78b1-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="a78b1-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="a78b1-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="a78b1-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="a78b1-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a78b1-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="a78b1-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="a78b1-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="a78b1-119">Идентификаторы RID, представляющие отдельные операционные системы, обычно имеют следующий формат: `[os].[version]-[architecture]-[additional qualifiers]`, где:</span><span class="sxs-lookup"><span data-stu-id="a78b1-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="a78b1-120">`[os]` — это моникер платформы или операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a78b1-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="a78b1-121">Например, `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="a78b1-122">`[version]` — это версия операционной системы в виде номера, разделенного точкой (`.`).</span><span class="sxs-lookup"><span data-stu-id="a78b1-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="a78b1-123">Например, `15.10`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="a78b1-124">Это **не должен быть** коммерческий номер версии, так как такой номер часто представляет отдельные версии операционной системы с различными контактными зонами API.</span><span class="sxs-lookup"><span data-stu-id="a78b1-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="a78b1-125">`[architecture]` — это архитектура процессора.</span><span class="sxs-lookup"><span data-stu-id="a78b1-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="a78b1-126">Например, `x86`, `x64`, `arm` или `arm64`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="a78b1-127">`[additional qualifiers]` дополнительно дифференцируют разные платформы.</span><span class="sxs-lookup"><span data-stu-id="a78b1-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="a78b1-128">Пример: `aot` или `corert`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-128">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="a78b1-129">Схема RID</span><span class="sxs-lookup"><span data-stu-id="a78b1-129">RID graph</span></span>

<span data-ttu-id="a78b1-130">Схема RID или резервная схема среды выполнения — это список идентификаторов RID, которые совместимы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="a78b1-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="a78b1-131">Идентификаторы RID определены в пакете [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="a78b1-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="a78b1-132">Список поддерживаемых идентификаторов RID и схема RID содержатся в файле [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), который находится в репозитории CoreFX.</span><span class="sxs-lookup"><span data-stu-id="a78b1-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="a78b1-133">В этом файле можно увидеть, что все идентификаторы RID, кроме основного, содержат оператор `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="a78b1-134">Эти операторы указывают совместимые RID.</span><span class="sxs-lookup"><span data-stu-id="a78b1-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="a78b1-135">Когда NuGet восстанавливает пакеты, он пытается найти точное совпадение для указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a78b1-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="a78b1-136">Если его не удается найти, NuGet проходит схему до тех пор, пока не найдет ближайшую совместимую систему в соответствии со схемой RID.</span><span class="sxs-lookup"><span data-stu-id="a78b1-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="a78b1-137">Ниже приведена запись для идентификатора RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="a78b1-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="a78b1-138">Приведенный выше идентификатор RID указывает, что `osx.10.12-x64` импортирует `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="a78b1-139">Таким образом, когда NuGet восстанавливает пакеты, он пытается найти в пакете точное совпадение для `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="a78b1-140">Например, если NuGet не удается найти определенную среду выполнения, он может восстановить пакеты, которые определяют среды выполнения `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="a78b1-141">В следующем примере показана немного большая схема RID, которая также указана в файле *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="a78b1-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="a78b1-142">Все идентификаторы RID в конечном итоге сопоставляются с корневым идентификатором RID `any`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="a78b1-143">При работе с идентификаторами RID следует учитывать некоторые моменты:</span><span class="sxs-lookup"><span data-stu-id="a78b1-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="a78b1-144">RID являются **непрозрачными строками**, и их следует рассматривать как "черные ящики".</span><span class="sxs-lookup"><span data-stu-id="a78b1-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="a78b1-145">Не следует создавать идентификаторы RID программным способом.</span><span class="sxs-lookup"><span data-stu-id="a78b1-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="a78b1-146">Используйте только те идентификаторы RID, которые уже определены для платформы.</span><span class="sxs-lookup"><span data-stu-id="a78b1-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="a78b1-147">Идентификаторы RID должны указываться точно. Предположения недопустимы.</span><span class="sxs-lookup"><span data-stu-id="a78b1-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="a78b1-148">Использование идентификаторов RID</span><span class="sxs-lookup"><span data-stu-id="a78b1-148">Using RIDs</span></span>

<span data-ttu-id="a78b1-149">Для использования идентификаторов RID необходимо знать, какие идентификаторы RID существуют.</span><span class="sxs-lookup"><span data-stu-id="a78b1-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="a78b1-150">В платформу регулярно добавляются новые идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="a78b1-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="a78b1-151">Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории CoreFX.</span><span class="sxs-lookup"><span data-stu-id="a78b1-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="a78b1-152">SDK для .NET Core 2.0 представляет концепцию переносных идентификаторов RID.</span><span class="sxs-lookup"><span data-stu-id="a78b1-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="a78b1-153">Это новые значения, добавленными в схему RID, которые не привязаны к конкретной версии или дистрибутиву ОС.</span><span class="sxs-lookup"><span data-stu-id="a78b1-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="a78b1-154">Их особенно удобно использовать при работе с несколькими дистрибутивами Linux.</span><span class="sxs-lookup"><span data-stu-id="a78b1-154">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="a78b1-155">Ниже представлен список наиболее распространенных RID, используемых для каждой ОС.</span><span class="sxs-lookup"><span data-stu-id="a78b1-155">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="a78b1-156">Он не охватывает значения `arm` или `corert`.</span><span class="sxs-lookup"><span data-stu-id="a78b1-156">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="a78b1-157">Идентификаторы RID для Windows</span><span class="sxs-lookup"><span data-stu-id="a78b1-157">Windows RIDs</span></span>

- <span data-ttu-id="a78b1-158">Портативные</span><span class="sxs-lookup"><span data-stu-id="a78b1-158">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="a78b1-159">Windows 7 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a78b1-159">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="a78b1-160">Windows 8 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a78b1-160">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="a78b1-161">Windows 8.1 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a78b1-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="a78b1-162">Windows 10 или Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a78b1-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="a78b1-163">Дополнительные сведения см. в разделе [Необходимые компоненты для .NET Core в Windows](windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a78b1-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="a78b1-164">Идентификаторы RID для Linux</span><span class="sxs-lookup"><span data-stu-id="a78b1-164">Linux RIDs</span></span>

- <span data-ttu-id="a78b1-165">Портативные</span><span class="sxs-lookup"><span data-stu-id="a78b1-165">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="a78b1-166">CentOS</span><span class="sxs-lookup"><span data-stu-id="a78b1-166">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="a78b1-167">Debian</span><span class="sxs-lookup"><span data-stu-id="a78b1-167">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="a78b1-168">Fedora</span><span class="sxs-lookup"><span data-stu-id="a78b1-168">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="a78b1-169">`fedora.25-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-169">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="a78b1-170">`fedora.26-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-170">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="a78b1-171">Gentoo (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-171">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="a78b1-172">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a78b1-172">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="a78b1-173">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a78b1-173">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="a78b1-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a78b1-174">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="a78b1-175">`rhel.6-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="a78b1-176">`rhel.7.3-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-176">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="a78b1-177">`rhel.7.4-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-177">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="a78b1-178">Tizen (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-178">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="a78b1-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a78b1-179">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="a78b1-180">Производные дистрибутивы Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a78b1-180">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="a78b1-181">`linuxmint.18.1-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-181">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="a78b1-182">Дополнительные сведения см. в разделе [Необходимые компоненты для .NET Core в Linux](linux-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a78b1-182">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="a78b1-183">Относительные идентификаторы macOS</span><span class="sxs-lookup"><span data-stu-id="a78b1-183">macOS RIDs</span></span>

<span data-ttu-id="a78b1-184">Относительные идентификаторы macOS используют старую фирменную символику "OSX".</span><span class="sxs-lookup"><span data-stu-id="a78b1-184">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="a78b1-185">`osx-x64` (.NET Core 2.0 или более поздние версии, минимальная версия — `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="a78b1-185">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="a78b1-186">`osx.10.12-x64` (.NET Core 1.1 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-186">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="a78b1-187">Дополнительные сведения см. в разделе [Необходимые компоненты для .NET Core в macOS](macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a78b1-187">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="a78b1-188">Идентификаторы RID для Android (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="a78b1-188">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="a78b1-189">См. также</span><span class="sxs-lookup"><span data-stu-id="a78b1-189">See also</span></span>

[<span data-ttu-id="a78b1-190">Идентификаторы среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a78b1-190">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
