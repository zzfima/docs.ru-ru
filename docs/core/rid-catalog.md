---
title: "Каталог идентификаторов сред выполнения (RID) в .NET Core"
description: "Сведения об идентификаторах сред выполнения и их использовании в .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a><span data-ttu-id="b39e2-104">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="b39e2-104">.NET Core Runtime IDentifier (RID) catalog</span></span>

## <a name="what-are-rids"></a><span data-ttu-id="b39e2-105">Что такое идентификатор RID</span><span class="sxs-lookup"><span data-stu-id="b39e2-105">What are RIDs?</span></span>
<span data-ttu-id="b39e2-106">RID — это сокращение от *Runtime IDentifier* (идентификатор среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="b39e2-106">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="b39e2-107">Идентификаторы RID служат для идентификации целевых операционных систем, в которых будет выполняться приложение или ресурс (то есть сборка).</span><span class="sxs-lookup"><span data-stu-id="b39e2-107">RIDs are used to identify target operating systems where an application or asset (that is, assembly) will run.</span></span> <span data-ttu-id="b39e2-108">Выглядят они следующим образом: ubuntu.14.04-x64, win7-x64, osx.10.11-x64.</span><span class="sxs-lookup"><span data-stu-id="b39e2-108">They look like this: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span></span> <span data-ttu-id="b39e2-109">Для пакетов с собственными зависимостями они указывают, на каких платформах можно восстановить пакет.</span><span class="sxs-lookup"><span data-stu-id="b39e2-109">For the packages with native dependencies, it will designate on which platforms the package can be restored.</span></span> 

<span data-ttu-id="b39e2-110">Важно отметить, что идентификаторы RID на самом деле являются непрозрачными строками.</span><span class="sxs-lookup"><span data-stu-id="b39e2-110">It is important to note that RIDs are really opaque strings.</span></span> <span data-ttu-id="b39e2-111">Это означает, что для выполнения операции, для которой они указаны, требуется их точное соответствие.</span><span class="sxs-lookup"><span data-stu-id="b39e2-111">This means that they have to match exactly for operations using them to work.</span></span> <span data-ttu-id="b39e2-112">В качестве примера возьмем ОС [Elementary OS](https://elementary.io/), которая является простым клоном Ubuntu 14.04.</span><span class="sxs-lookup"><span data-stu-id="b39e2-112">As an example, let us consider the case of [Elementary OS](https://elementary.io/), which is a straightforward clone of Ubuntu 14.04.</span></span> <span data-ttu-id="b39e2-113">Хотя платформа .NET Core и интерфейс командной строки (CLI) работают в этой версии Ubuntu, если вы попытаетесь использовать их в Elementary OS без каких-либо изменений, операция восстановления любого пакета завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="b39e2-113">Although .NET Core and CLI work on top of that version of Ubuntu, if you try to use them on Elementary OS without any modifications, the restore operation for any package will fail.</span></span> <span data-ttu-id="b39e2-114">Связано это с тем, что в настоящее время нет идентификатора RID, указывающего на Elementary OS как на целевую платформу.</span><span class="sxs-lookup"><span data-stu-id="b39e2-114">This is because we currently don't have a RID that designates Elementary OS as a platform.</span></span> 

<span data-ttu-id="b39e2-115">Идентификаторы RID, представляющие отдельные операционные системы, обычно имеют следующий формат: `[os].[version]-[arch]`, где:</span><span class="sxs-lookup"><span data-stu-id="b39e2-115">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[arch]` where:</span></span>
- <span data-ttu-id="b39e2-116">`[os]` — это моникер операционной системы, например `ubuntu`;</span><span class="sxs-lookup"><span data-stu-id="b39e2-116">`[os]` is the operating system moniker, for example, `ubuntu`.</span></span>
- <span data-ttu-id="b39e2-117">`[version]` — это версия операционной системы в виде номера, разделенного точкой (`.`), например `15.10`. Такой номер достаточно точен для нацеливания ресурсов на соответствующие версии платформенных интерфейсов API операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-117">`[version]` is the operating system version in the form of a dot (`.`) separated version number, for example, `15.10`, accurate enough to reasonably enable assets to target operating system platform APIs represented by that version.</span></span>
  - <span data-ttu-id="b39e2-118">Это **не должен** быть коммерческий номер версии, так как такой номер часто представляет отдельные версии операционной системы с различными контактными зонами API;</span><span class="sxs-lookup"><span data-stu-id="b39e2-118">This **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>
- <span data-ttu-id="b39e2-119">`[arch]` — это архитектура процессора, например `x86`, `x64`, `arm`, `arm64` и т. д.</span><span class="sxs-lookup"><span data-stu-id="b39e2-119">`[arch]` is the processor architecture, for example, `x86`, `x64`, `arm`, `arm64`, etc.</span></span>

<span data-ttu-id="b39e2-120">Схема RID определяется в пакете с именем `Microsoft.NETCore.Platforms` в файле `runtime.json`, который можно просмотреть в [репозитории CoreFX](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span><span class="sxs-lookup"><span data-stu-id="b39e2-120">The RID graph is defined in a package called `Microsoft.NETCore.Platforms` in a file called `runtime.json`, which you can see on the [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span></span> <span data-ttu-id="b39e2-121">В этом файле можно увидеть, что некоторые идентификаторы RID содержат оператор `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="b39e2-121">If you use this file, you will notice that some of the RIDs have an `"#import"` statement in them.</span></span> <span data-ttu-id="b39e2-122">Это оператор совместимости.</span><span class="sxs-lookup"><span data-stu-id="b39e2-122">These statements are compatibility statements.</span></span> <span data-ttu-id="b39e2-123">Он означает, что идентификатор RID, содержащий в себе импортированный идентификатор RID, может быть целевым для восстановления пакетов, предназначенных для импортированного RID.</span><span class="sxs-lookup"><span data-stu-id="b39e2-123">That means that a RID that has an imported RID in it can be a target for restoring packages for that RID.</span></span> <span data-ttu-id="b39e2-124">Немного запутано, но давайте рассмотрим пример.</span><span class="sxs-lookup"><span data-stu-id="b39e2-124">Slightly confusing, but let's look at an example.</span></span> <span data-ttu-id="b39e2-125">Возьмем Mac OS.</span><span class="sxs-lookup"><span data-stu-id="b39e2-125">Let's take a look at macOS:</span></span>

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
<span data-ttu-id="b39e2-126">Приведенный выше идентификатор RID указывает, что `osx.10.11-x64` импортирует `osx.10.10-x64`.</span><span class="sxs-lookup"><span data-stu-id="b39e2-126">The above RID specifies that `osx.10.11-x64` imports `osx.10.10-x64`.</span></span> <span data-ttu-id="b39e2-127">Это означает, что при восстановлении пакетов система NuGet сможет восстанавливать пакеты, требующие `osx.10.10-x64`, в `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="b39e2-127">This means that when restoring packages, NuGet will be able to restore packages that specify that they need `osx.10.10-x64` on `osx.10.11-x64`.</span></span>

<span data-ttu-id="b39e2-128">Немного более развернутый пример схемы RID</span><span class="sxs-lookup"><span data-stu-id="b39e2-128">A slightly bigger example RID graph:</span></span>  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

<span data-ttu-id="b39e2-129">Все идентификаторы RID в конечном итоге сопоставляются с корневым идентификатором RID `any`.</span><span class="sxs-lookup"><span data-stu-id="b39e2-129">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="b39e2-130">Хотя их использование не представляется сложным, есть ряд особенностей, которые следует учитывать при работе с идентификаторами RID.</span><span class="sxs-lookup"><span data-stu-id="b39e2-130">Although they look easy enough to use, there are some special things about RIDs that you have to keep in mind when working with them:</span></span>

* <span data-ttu-id="b39e2-131">Они являются **непрозрачными строками**, и их следует рассматривать как "черные ящики".</span><span class="sxs-lookup"><span data-stu-id="b39e2-131">They are **opaque strings** and should be treated as black boxes</span></span>
    * <span data-ttu-id="b39e2-132">Не следует формировать идентификаторы RID программным способом.</span><span class="sxs-lookup"><span data-stu-id="b39e2-132">You should not construct RIDs programmatically</span></span>
* <span data-ttu-id="b39e2-133">Используйте только идентификаторы RID, которые уже определены для платформы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-133">You need to use the RIDs that are already defined for the platform and this document shows that</span></span>
* <span data-ttu-id="b39e2-134">Идентификаторы RID должны указываться точно, поэтому обращайтесь к этому документу для определения идентификаторов RID, необходимых для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="b39e2-134">The RIDs do need to be specific so don't assume anything from the actual RID value; please consult this document to determine which RID(s) you need for a given platform</span></span>

## <a name="using-rids"></a><span data-ttu-id="b39e2-135">Использование идентификаторов RID</span><span class="sxs-lookup"><span data-stu-id="b39e2-135">Using RIDs</span></span>
<span data-ttu-id="b39e2-136">Для использования идентификаторов RID необходимо знать какие идентификаторы RID существуют.</span><span class="sxs-lookup"><span data-stu-id="b39e2-136">In order to use RIDs, you have to know which RIDs there are.</span></span> <span data-ttu-id="b39e2-137">В платформу регулярно добавляются новые идентификаторы RID.</span><span class="sxs-lookup"><span data-stu-id="b39e2-137">New RIDs are added regularly to the platform.</span></span> <span data-ttu-id="b39e2-138">Чтобы получить актуальный список, просмотрите файл [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории CoreFX.</span><span class="sxs-lookup"><span data-stu-id="b39e2-138">For the latest version, please check the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

> [!NOTE]
> <span data-ttu-id="b39e2-139">Мы работаем над тем, чтобы представить эту информацию в более интерактивной форме.</span><span class="sxs-lookup"><span data-stu-id="b39e2-139">We are working towards getting this information into a more interactive form.</span></span> <span data-ttu-id="b39e2-140">Когда мы решим эту задачу, данная страница будет обновлена и на ней будут приведены ссылки на соответствующее средство и документацию по его использованию.</span><span class="sxs-lookup"><span data-stu-id="b39e2-140">When that happens, this page will be updated to point to that tool and/or its usage documentation.</span></span> 

## <a name="windows-rids"></a><span data-ttu-id="b39e2-141">Идентификаторы RID для Windows</span><span class="sxs-lookup"><span data-stu-id="b39e2-141">Windows RIDs</span></span>

* <span data-ttu-id="b39e2-142">Windows 7 или Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b39e2-142">Windows 7 / Windows Server 2008 R2</span></span>
    * `win7-x64`
    * `win7-x86`
* <span data-ttu-id="b39e2-143">Windows 8 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b39e2-143">Windows 8 / Windows Server 2012</span></span>
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* <span data-ttu-id="b39e2-144">Windows 8.1 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b39e2-144">Windows 8.1 / Windows Server 2012 R2</span></span>
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* <span data-ttu-id="b39e2-145">Windows 10 или Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b39e2-145">Windows 10 / Windows Server 2016</span></span>
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a><span data-ttu-id="b39e2-146">Идентификаторы RID для Linux</span><span class="sxs-lookup"><span data-stu-id="b39e2-146">Linux RIDs</span></span>

* <span data-ttu-id="b39e2-147">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="b39e2-147">Red Hat Enterprise Linux</span></span>
    * `rhel.7-x64`
* <span data-ttu-id="b39e2-148">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b39e2-148">Ubuntu</span></span>
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* <span data-ttu-id="b39e2-149">CentOS</span><span class="sxs-lookup"><span data-stu-id="b39e2-149">CentOS</span></span>
    * `centos.7-x64`
* <span data-ttu-id="b39e2-150">Debian</span><span class="sxs-lookup"><span data-stu-id="b39e2-150">Debian</span></span>
    * `debian.8-x64`
* <span data-ttu-id="b39e2-151">Fedora</span><span class="sxs-lookup"><span data-stu-id="b39e2-151">Fedora</span></span>
    * `fedora.23-x64`
    * `fedora.24-x64`
* <span data-ttu-id="b39e2-152">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="b39e2-152">OpenSUSE</span></span>
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* <span data-ttu-id="b39e2-153">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="b39e2-153">Oracle Linux</span></span>
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* <span data-ttu-id="b39e2-154">Производные дистрибутивы Ubuntu, поддерживаемые в настоящее время</span><span class="sxs-lookup"><span data-stu-id="b39e2-154">Currently supported Ubuntu derivatives</span></span> 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a><span data-ttu-id="b39e2-155">Идентификаторы RID для OS X</span><span class="sxs-lookup"><span data-stu-id="b39e2-155">OS X RIDs</span></span>

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

