---
title: "Каталог идентификаторов сред выполнения (RID) в .NET Core"
description: "Сведения об идентификаторах сред выполнения и их использовании в .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 067f9cfc283a14b7ea59a7454b7f593ce6eb5806
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="d4f5e-103">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4f5e-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="d4f5e-104">RID — это сокращение от *Runtime IDentifier* (идентификатор среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="d4f5e-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="d4f5e-105">Идентификаторы RID служат для идентификации целевых платформ, на которых выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="d4f5e-106">Они используются пакетами .NET для представления ресурсов, специфичных для платформы, в пакетах NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="d4f5e-107">Некоторые примеры идентификаторов RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` или `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="d4f5e-108">Для пакетов с собственными зависимостями они указывают, на каких платформах можно восстановить пакет.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="d4f5e-109">Идентификаторы RID можно задать в элементе `<RuntimeIdentifier>` вашего файла проекта.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-109">RIDs can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="d4f5e-110">Они также используются с помощью параметра `--runtime` со следующими [командами интерфейса командной строки .NET Core](./tools/index.md):</span><span class="sxs-lookup"><span data-stu-id="d4f5e-110">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="d4f5e-111">dotnet build</span><span class="sxs-lookup"><span data-stu-id="d4f5e-111">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="d4f5e-112">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="d4f5e-112">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="d4f5e-113">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="d4f5e-113">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="d4f5e-114">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="d4f5e-114">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="d4f5e-115">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="d4f5e-115">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="d4f5e-116">dotnet run</span><span class="sxs-lookup"><span data-stu-id="d4f5e-116">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="d4f5e-117">dotnet store</span><span class="sxs-lookup"><span data-stu-id="d4f5e-117">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="d4f5e-118">Идентификаторы RID, представляющие отдельные операционные системы, обычно имеют следующий формат: `[os].[version]-[architecture]-[additional qualifiers]`, где:</span><span class="sxs-lookup"><span data-stu-id="d4f5e-118">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="d4f5e-119">`[os]` — это моникер платформы или операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-119">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="d4f5e-120">Например, `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-120">For example, `ubuntu`.</span></span>

- <span data-ttu-id="d4f5e-121">`[version]` — это версия операционной системы в виде номера, разделенного точкой (`.`).</span><span class="sxs-lookup"><span data-stu-id="d4f5e-121">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="d4f5e-122">Например, `15.10`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-122">For example, `15.10`.</span></span>

  - <span data-ttu-id="d4f5e-123">Это **не должен быть** коммерческий номер версии, так как такой номер часто представляет отдельные версии операционной системы с различными контактными зонами API.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-123">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="d4f5e-124">`[architecture]` — это архитектура процессора.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-124">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="d4f5e-125">Например, `x86`, `x64`, `arm` или `arm64`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-125">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="d4f5e-126">`[additional qualifiers]` дополнительно дифференцируют разные платформы.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-126">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="d4f5e-127">Пример: `aot` или `corert`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-127">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="d4f5e-128">Схема RID</span><span class="sxs-lookup"><span data-stu-id="d4f5e-128">RID graph</span></span>

<span data-ttu-id="d4f5e-129">Схема RID или резервная схема среды выполнения — это список идентификаторов RID, которые совместимы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-129">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="d4f5e-130">Идентификаторы RID определены в пакете [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="d4f5e-130">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="d4f5e-131">Список поддерживаемых идентификаторов RID и схема RID содержатся в файле [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), который находится в репозитории CoreFX.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-131">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="d4f5e-132">В этом файле можно увидеть, что все идентификаторы RID, кроме основного, содержат оператор `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-132">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="d4f5e-133">Эти операторы указывают совместимые RID.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-133">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="d4f5e-134">Когда NuGet восстанавливает пакеты, он пытается найти точное совпадение для указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-134">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="d4f5e-135">Если его не удается найти, NuGet проходит схему до тех пор, пока не найдет ближайшую совместимую систему в соответствии со схемой RID.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-135">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="d4f5e-136">Ниже приведена запись для идентификатора RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="d4f5e-136">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="d4f5e-137">Приведенный выше идентификатор RID указывает, что `osx.10.12-x64` импортирует `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-137">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="d4f5e-138">Таким образом, когда NuGet восстанавливает пакеты, он пытается найти в пакете точное совпадение для `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-138">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="d4f5e-139">Например, если NuGet не удается найти определенную среду выполнения, он может восстановить пакеты, которые определяют среды выполнения `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-139">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="d4f5e-140">В следующем примере показана немного большая схема RID, которая также указана в файле *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="d4f5e-140">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

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

<span data-ttu-id="d4f5e-141">Все идентификаторы RID в конечном итоге сопоставляются с корневым идентификатором RID `any`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-141">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="d4f5e-142">При работе с идентификаторами RID следует учитывать некоторые моменты:</span><span class="sxs-lookup"><span data-stu-id="d4f5e-142">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="d4f5e-143">RID являются **непрозрачными строками**, и их следует рассматривать как "черные ящики".</span><span class="sxs-lookup"><span data-stu-id="d4f5e-143">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="d4f5e-144">Не следует создавать идентификаторы RID программным способом.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-144">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="d4f5e-145">Используйте только те идентификаторы RID, которые уже определены для платформы.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-145">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="d4f5e-146">Идентификаторы RID должны указываться точно. Предположения недопустимы.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-146">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="d4f5e-147">Использование идентификаторов RID</span><span class="sxs-lookup"><span data-stu-id="d4f5e-147">Using RIDs</span></span>

<span data-ttu-id="d4f5e-148">Для использования идентификаторов RID необходимо знать, какие идентификаторы RID существуют.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-148">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="d4f5e-149">В платформу регулярно добавляются новые идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-149">New values are added regularly to the platform.</span></span>
<span data-ttu-id="d4f5e-150">Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории CoreFX.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-150">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="d4f5e-151">SDK для .NET Core 2.0 представляет концепцию переносных идентификаторов RID.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-151">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="d4f5e-152">Это новые значения, добавленными в схему RID, которые не привязаны к конкретной версии или дистрибутиву ОС.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-152">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="d4f5e-153">Они особенно полезна при работе с несколькими дистрибутивы Linux.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-153">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="d4f5e-154">Ниже представлен список наиболее распространенных RID, используемых для каждой ОС.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-154">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="d4f5e-155">Он не охватывает значения `arm` или `corert`.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-155">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="d4f5e-156">Идентификаторы RID для Windows</span><span class="sxs-lookup"><span data-stu-id="d4f5e-156">Windows RIDs</span></span>

- <span data-ttu-id="d4f5e-157">Портативные</span><span class="sxs-lookup"><span data-stu-id="d4f5e-157">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="d4f5e-158">Windows 7 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d4f5e-158">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="d4f5e-159">Windows 8 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d4f5e-159">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="d4f5e-160">Windows 8.1 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d4f5e-160">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="d4f5e-161">Windows 10 или Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d4f5e-161">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="d4f5e-162">В разделе [необходимых компонентов для .NET Core в Windows](windows-prerequisites.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-162">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="d4f5e-163">Идентификаторы RID для Linux</span><span class="sxs-lookup"><span data-stu-id="d4f5e-163">Linux RIDs</span></span>

- <span data-ttu-id="d4f5e-164">Портативные</span><span class="sxs-lookup"><span data-stu-id="d4f5e-164">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="d4f5e-165">CentOS</span><span class="sxs-lookup"><span data-stu-id="d4f5e-165">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="d4f5e-166">Debian</span><span class="sxs-lookup"><span data-stu-id="d4f5e-166">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="d4f5e-167">Fedora</span><span class="sxs-lookup"><span data-stu-id="d4f5e-167">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="d4f5e-168">`fedora.25-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-168">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="d4f5e-169">`fedora.26-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-169">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="d4f5e-170">Gentoo (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-170">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="d4f5e-171">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d4f5e-171">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="d4f5e-172">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="d4f5e-172">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="d4f5e-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="d4f5e-173">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="d4f5e-174">`rhel.6-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-174">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="d4f5e-175">`rhel.7.3-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-175">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="d4f5e-176">`rhel.7.4-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-176">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="d4f5e-177">Tizen (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-177">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="d4f5e-178">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4f5e-178">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="d4f5e-179">Производные дистрибутивы Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d4f5e-179">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="d4f5e-180">`linuxmint.18.1-x64` (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-180">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="d4f5e-181">В разделе [необходимых компонентов для .NET Core для Linux](linux-prerequisites.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-181">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="d4f5e-182">идентификаторы RID macOS</span><span class="sxs-lookup"><span data-stu-id="d4f5e-182">macOS RIDs</span></span>

<span data-ttu-id="d4f5e-183">идентификаторы RID macOS использовать старые «OSX» фирменной символики.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-183">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="d4f5e-184">`osx-x64`(.NET core 2.0 или более поздней версии, минимальная версия — `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-184">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="d4f5e-185">`osx.10.12-x64` (.NET Core 1.1 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-185">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="d4f5e-186">В разделе [необходимых компонентов для .NET Core на macOS](macos-prerequisites.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="d4f5e-186">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="d4f5e-187">Идентификаторы RID для Android (.NET Core 2.0 или более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="d4f5e-187">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="d4f5e-188">См. также</span><span class="sxs-lookup"><span data-stu-id="d4f5e-188">See also</span></span>

[<span data-ttu-id="d4f5e-189">Идентификаторы среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d4f5e-189">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
