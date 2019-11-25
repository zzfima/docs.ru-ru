---
title: Строгое именование и библиотеки .NET
description: Рекомендации по использованию строгого именования для библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: 3e7cc9a3a1be05d8fcb02b34f7027126697d15d0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196971"
---
# <a name="strong-naming"></a><span data-ttu-id="cd6f0-103">Строгое именование</span><span class="sxs-lookup"><span data-stu-id="cd6f0-103">Strong naming</span></span>

<span data-ttu-id="cd6f0-104">Строгим именованием называется подписывание сборки с использованием ключа. Полученная сборка считается [сборкой со строгими именами](../assembly/strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="cd6f0-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../assembly/strong-named.md).</span></span> <span data-ttu-id="cd6f0-105">Сборка со строгими именами получает уникальный идентификатор, составленный из имени и номера версии этой сборки, предотвращая возникновение конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="cd6f0-106">Строгое именование неудобно тем, что .NET Framework на платформе Windows принудительно применяет строгую загрузку для сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="cd6f0-107">Ссылка на сборку со строгими именами должна точно соответствовать версии, которая указана в этой сборке. Это вынуждает разработчиков [настраивать переадресацию привязок](../../framework/configure-apps/redirect-assembly-versions.md) при использовании такой сборки:</span><span class="sxs-lookup"><span data-stu-id="cd6f0-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="cd6f0-108">Если разработчик .NET выражает недовольство строгим именованием, он скорее всего имеет в виду именно строгую загрузку сборок.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="cd6f0-109">К счастью, эта проблема касается только платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="cd6f0-110">В .NET Core, Xamarin, универсальной платформе Windows и большинстве других реализаций .NET не применяется строгая загрузка сборок, что избавляет нас от основного недостатка строгого именования.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="cd6f0-111">Еще один важный аспект строгого именования — оно "заразно", то есть любая сборка со строгими именами может содержать ссылки только на другие сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="cd6f0-112">Если ваша библиотека не использует строгое именование, ее не смогут использовать другие разработчики, которые создают приложения или библиотеки с обязательным строгим именованием.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="cd6f0-113">Ниже перечислены преимущества строгого именования:</span><span class="sxs-lookup"><span data-stu-id="cd6f0-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="cd6f0-114">Сборку можно указывать и использовать в других сборках со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="cd6f0-115">Сборку можно хранить в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="cd6f0-116">Сборку можно загружать параллельно с другими версиями этой сборки.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="cd6f0-117">Параллельная загрузка нескольких версий сборки часто используется в приложениях с поддержкой подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="cd6f0-118">Создание библиотек .NET со строгими именами</span><span class="sxs-lookup"><span data-stu-id="cd6f0-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="cd6f0-119">Для всех библиотек .NET с открытым исходным кодом следует применять строгое именование.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="cd6f0-120">Строгое именование сборки позволяет большинству пользователей ее использовать, а проблема со строгой загрузкой касается только пользователей .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="cd6f0-121">Это руководство относится ко всем свободно распространяемым библиотекам .NET, например к библиотекам .NET на сайте nuget.org. Строгое именование не является обязательным для большинства приложений .NET. По умолчанию его не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="cd6f0-122">**✔️ ДОПУСТИМО.** Вы можете использовать строгое именование для сборок библиотеки.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="cd6f0-123">**✔️ ДОПУСТИМО.** Вы можете добавлять ключ строгого именования в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-123">**✔️ CONSIDER** adding the strong naming key to your source control system.</span></span>

> <span data-ttu-id="cd6f0-124">Общедоступный ключ позволяет разработчикам изменять и повторно компилировать исходный код библиотеки с тем же ключом.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>
> 
> <span data-ttu-id="cd6f0-125">Ключ строгого именования не следует делать открытым, если ранее он использовался для предоставления особых разрешений в [сценариях частичного доверия](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span><span class="sxs-lookup"><span data-stu-id="cd6f0-125">You shouldn't make the strong naming key public if it has been used in the past to give special permissions in [partial-trust scenarios](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span></span> <span data-ttu-id="cd6f0-126">Такая публикация может поставить под угрозу существующие среды.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-126">Otherwise, you might compromise existing environments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd6f0-127">Если важно поддерживать для кода идентификацию издателя, мы рекомендуем применить [Authenticode](/windows-hardware/drivers/install/authenticode) и [Подписывание пакетов NuGet](/nuget/create-packages/sign-a-package).</span><span class="sxs-lookup"><span data-stu-id="cd6f0-127">When the identity of the publisher of the code is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="cd6f0-128">Управление доступом для кода (CAS) не следует применять в качестве меры безопасности.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-128">Code Access Security (CAS) should not be used as a security mitigation.</span></span>

<span data-ttu-id="cd6f0-129">**✔️ ДОПУСТИМО.** Вы можете увеличивать номер версии для сборки только для основных номеров версии, чтобы избавить пользователей от лишних переадресаций привязок и частого их обновления.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-129">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="cd6f0-130">См. сведения о [версиях сборок и управлении версиями](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="cd6f0-130">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="cd6f0-131">**❌ НЕЛЬЗЯ.** Не добавляйте, не удаляйте и не изменяйте ключ строгого именования.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-131">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="cd6f0-132">Изменение указанного для сборки ключа строгого именования изменяет идентификатор сборки и нарушает работу любого скомпилированного кода, который использует эту сборку.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-132">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="cd6f0-133">См. сведения о [критических изменениях на уровне двоичного кода](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="cd6f0-133">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="cd6f0-134">**❌ НЕЛЬЗЯ.** Не публикуйте версии библиотеки со строгим и нестрогим именем.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-134">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="cd6f0-135">Например, `Contoso.Api` и `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-135">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="cd6f0-136">Публикация двух вариантов пакета приводит к рассогласованию всей экосистемы разработки.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-136">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="cd6f0-137">Кроме того, если некоторому приложению потребуются оба варианта этого пакета, могут возникать конфликты имен.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-137">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="cd6f0-138">Платформа .NET рассматривает такие пакеты как разные типы из разных сборок.</span><span class="sxs-lookup"><span data-stu-id="cd6f0-138">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cd6f0-139">[Назад](cross-platform-targeting.md)
>[Вперед](nuget.md)</span><span class="sxs-lookup"><span data-stu-id="cd6f0-139">[Previous](cross-platform-targeting.md)
[Next](nuget.md)</span></span>
