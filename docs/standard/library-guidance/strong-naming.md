---
title: Строгое именование и библиотеки .NET
description: Практические рекомендации для строгого именования библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372813"
---
# <a name="strong-naming"></a><span data-ttu-id="44986-103">Строгое именование</span><span class="sxs-lookup"><span data-stu-id="44986-103">Strong naming</span></span>

<span data-ttu-id="44986-104">Строгое именование ссылается на подпись сборки с ключом, создания [сборки со строгими именами](../../framework/app-domains/strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="44986-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../../framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="44986-105">При сборки со строгим именем, он создает уникальное удостоверение, основанное на номер версии имя и сборку, и поможет избежать конфликтов сборок.</span><span class="sxs-lookup"><span data-stu-id="44986-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="44986-106">Строгое именование недостаток в том, что .NET Framework на Windows позволяет strict загрузки сборок, после сборки есть строгое имя.</span><span class="sxs-lookup"><span data-stu-id="44986-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="44986-107">Ссылку на сборку со строгим именем должны точно совпадать с версией, ссылается на сборку, чтобы заставлять разработчиков придумывать [Настройка перенаправления привязки](../../framework/configure-apps/redirect-assembly-versions.md) при использовании сборки:</span><span class="sxs-lookup"><span data-stu-id="44986-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

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

<span data-ttu-id="44986-108">Разработчикам .NET жалуются на строгое именование, что они обычно жалуется при строгом загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="44986-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="44986-109">К счастью эту проблему изолирован на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44986-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="44986-110">.NET core, Xamarin, универсальной платформы Windows и большинство других реализаций .NET нет строгой загрузки сборки и удаляет основной недостаток использования строгих имен.</span><span class="sxs-lookup"><span data-stu-id="44986-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="44986-111">Одним важным аспектом строгих имен — это популярный: надежный с именем сборки могут только одну ссылку других надежный с именем сборки.</span><span class="sxs-lookup"><span data-stu-id="44986-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="44986-112">Если библиотека не надежный с именем, затем был исключен разработчиков, создающих приложения или библиотеки, которому требуется строгое именование от его использования.</span><span class="sxs-lookup"><span data-stu-id="44986-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="44986-113">Приведены преимущества строгое именование.</span><span class="sxs-lookup"><span data-stu-id="44986-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="44986-114">Сборки можно ссылаться и использовать в других сборках со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="44986-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="44986-115">Сборки могут храниться в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="44986-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="44986-116">Сборка может быть загружена параллельно с другими версиями сборки.</span><span class="sxs-lookup"><span data-stu-id="44986-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="44986-117">Загрузка сборки Side-by-side часто требуется приложений с помощью подключаемого модуля архитектур.</span><span class="sxs-lookup"><span data-stu-id="44986-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="44986-118">Создайте надежный с именем библиотеки .NET</span><span class="sxs-lookup"><span data-stu-id="44986-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="44986-119">Следует строгое именование .NET библиотек открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="44986-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="44986-120">Строгое именование сборки гарантирует, большинство пользователей можно использовать его и строгом загрузки только сборок влияет на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44986-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="44986-121">Это руководство относится к свободно распространяемые библиотеки .NET, таких как библиотеки .NET опубликованы на сайте NuGet.org. Строгое именование не является обязательным для большинства приложений .NET и не должна осуществляться по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44986-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="44986-122">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** строгого именования сборки библиотеки.</span><span class="sxs-lookup"><span data-stu-id="44986-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="44986-123">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** проверки в ключ, используемый для строгого имени в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="44986-123">**✔️ CONSIDER** checking in the key used to strong name into your source control system.</span></span>

> <span data-ttu-id="44986-124">Общедоступные ключ позволяет разработчикам измените и перекомпилируйте исходный код библиотеки с тем же ключом.</span><span class="sxs-lookup"><span data-stu-id="44986-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44986-125">При необходимости шифрования удостоверений [Authenticode](/windows-hardware/drivers/install/authenticode) и [Подписание пакета NuGet](/nuget/create-packages/sign-a-package) рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="44986-125">When a cryptographic identity is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="44986-126">Строгое именование не следует по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="44986-126">Strong naming should not be used for security considerations.</span></span>

<span data-ttu-id="44986-127">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** увеличение версии сборки на изменения только основной номер версии, помогающие пользователям сократить переадресации привязок, и как часто они обновлены.</span><span class="sxs-lookup"><span data-stu-id="44986-127">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="44986-128">Дополнительные сведения о [управление версиями и версию сборки](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="44986-128">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="44986-129">**❌ НЕ** добавления, удаления или изменения ключа строгого именования.</span><span class="sxs-lookup"><span data-stu-id="44986-129">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="44986-130">Изменение сборки строгого именования ключ изменяет удостоверение сборки и разбивает скомпилированный код, который его использует.</span><span class="sxs-lookup"><span data-stu-id="44986-130">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="44986-131">Дополнительные сведения см. в разделе [двоичных критические изменения](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="44986-131">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="44986-132">**❌ НЕ** публикации со строгим именем и не-со строгими именами версий библиотеки.</span><span class="sxs-lookup"><span data-stu-id="44986-132">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="44986-133">Например, `Contoso.Api` и `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="44986-133">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="44986-134">Публикация две вилки пакеты разработчика в экономичном системы.</span><span class="sxs-lookup"><span data-stu-id="44986-134">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="44986-135">Кроме того в зависимости от того, оба пакета приложения заканчивается разработчика могут возникнуть конфликты имя типа.</span><span class="sxs-lookup"><span data-stu-id="44986-135">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="44986-136">Что касается .NET это разные типы в разных сборках.</span><span class="sxs-lookup"><span data-stu-id="44986-136">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="44986-137">[Назад](./cross-platform-targeting.md)
[Вперед](./nuget.md)</span><span class="sxs-lookup"><span data-stu-id="44986-137">[Previous](./cross-platform-targeting.md)
[Next](./nuget.md)</span></span>
