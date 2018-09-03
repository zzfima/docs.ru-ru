---
title: Разработка библиотек с помощью кроссплатформенных средств
description: Узнайте, как создавать библиотеки для .NET с помощью программ командной строки .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 05/01/2017
ms.openlocfilehash: a6db7a15c484122600afd54814d19ea11bd1abc1
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43256200"
---
# <a name="developing-libraries-with-cross-platform-tools"></a><span data-ttu-id="e18a6-103">Разработка библиотек с помощью кроссплатформенных средств</span><span class="sxs-lookup"><span data-stu-id="e18a6-103">Developing Libraries with Cross Platform Tools</span></span>

<span data-ttu-id="e18a6-104">В этой статье рассматривается создание библиотек для .NET с помощью кроссплатформенных средств интерфейса командной строки (CLI).</span><span class="sxs-lookup"><span data-stu-id="e18a6-104">This article covers how to write libraries for .NET using cross-platform CLI tools.</span></span> <span data-ttu-id="e18a6-105">CLI предоставляет эффективный и низкоуровневый интерфейс, работающий в любых поддерживаемых операционных системах.</span><span class="sxs-lookup"><span data-stu-id="e18a6-105">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="e18a6-106">Вы по-прежнему можете создавать библиотеки с помощью Visual Studio. Если вы предпочитаете такой способ, обратитесь к [руководству по Visual Studio](libraries-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e18a6-106">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](libraries-with-vs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e18a6-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e18a6-107">Prerequisites</span></span>

<span data-ttu-id="e18a6-108">На компьютере должны быть установлены [пакет SDK и интерфейс CLI для .NET Core ](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="e18a6-108">You need [the .NET Core SDK and CLI](https://www.microsoft.com/net/core) installed on your machine.</span></span>

<span data-ttu-id="e18a6-109">При работе с разделами, в которых используются различные версии .NET Framework, на компьютере с ОС Windows должна быть установлена платформа [.NET Framework](http://getdotnet.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="e18a6-109">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](http://getdotnet.azurewebsites.net/) installed on a Windows machine.</span></span>

<span data-ttu-id="e18a6-110">Кроме того, если необходимо поддерживать целевые платформы .NET Framework предыдущих версий, требуется установить пакеты нацеливания и пакеты для разработчиков, предназначенные для предыдущих версий платформы, со [страницы целевых платформ .NET](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span><span class="sxs-lookup"><span data-stu-id="e18a6-110">Additionally, if you wish to support older .NET Framework targets, you need to install targeting/developer packs for older framework versions from the [.NET target platforms page](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span></span> <span data-ttu-id="e18a6-111">См. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="e18a6-111">Refer to this table:</span></span>

| <span data-ttu-id="e18a6-112">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e18a6-112">.NET Framework Version</span></span> | <span data-ttu-id="e18a6-113">Скачиваемые компоненты</span><span class="sxs-lookup"><span data-stu-id="e18a6-113">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="e18a6-114">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e18a6-114">4.6.1</span></span>                  | <span data-ttu-id="e18a6-115">.NET Framework 4.6.1 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="e18a6-115">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="e18a6-116">4.6</span><span class="sxs-lookup"><span data-stu-id="e18a6-116">4.6</span></span>                    | <span data-ttu-id="e18a6-117">.NET Framework 4.6 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="e18a6-117">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="e18a6-118">4.5.2</span><span class="sxs-lookup"><span data-stu-id="e18a6-118">4.5.2</span></span>                  | <span data-ttu-id="e18a6-119">.NET Framework 4.5.2 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="e18a6-119">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="e18a6-120">4.5.1</span><span class="sxs-lookup"><span data-stu-id="e18a6-120">4.5.1</span></span>                  | <span data-ttu-id="e18a6-121">.NET Framework 4.5.1 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="e18a6-121">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="e18a6-122">4.5</span><span class="sxs-lookup"><span data-stu-id="e18a6-122">4.5</span></span>                    | <span data-ttu-id="e18a6-123">Пакет средств разработки программного обеспечения Windows для Windows 8</span><span class="sxs-lookup"><span data-stu-id="e18a6-123">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="e18a6-124">4.0</span><span class="sxs-lookup"><span data-stu-id="e18a6-124">4.0</span></span>                    | <span data-ttu-id="e18a6-125">Пакет SDK для Windows 7 и .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="e18a6-125">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="e18a6-126">2.0, 3.0 и 3.5</span><span class="sxs-lookup"><span data-stu-id="e18a6-126">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="e18a6-127">Среда выполнения .NET Framework 3.5 с пакетом обновления 1 (SP1) (либо версия для Windows 8 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="e18a6-127">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="e18a6-128">Нацеливание на .NET Standard</span><span class="sxs-lookup"><span data-stu-id="e18a6-128">How to target the .NET Standard</span></span>

<span data-ttu-id="e18a6-129">Если вы недостаточно хорошо знакомы с платформой .NET Standard, дополнительные сведения см. в [этом разделе](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="e18a6-129">If you're not quite familiar with the .NET Standard, refer to the [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="e18a6-130">В этом разделе есть таблица, в которой версии .NET Standard сопоставляются с различными реализациями:</span><span class="sxs-lookup"><span data-stu-id="e18a6-130">In that article, there is a table which maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

<span data-ttu-id="e18a6-131">Вот что значит эта таблица в контексте создания библиотеки:</span><span class="sxs-lookup"><span data-stu-id="e18a6-131">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="e18a6-132">Версия .NET Standard, которую вы выберете, будет компромиссом между наличием новейших API-интерфейсов и возможностью нацеливать приложение на большее количество реализаций .NET и версий .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e18a6-132">The version of the .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="e18a6-133">Диапазон целевых платформ и версий определяется выбранной версией `netstandardX.X` (где `X.X` — это номер версии), которая добавляется в файл проекта (`.csproj` или `.fsproj`).</span><span class="sxs-lookup"><span data-stu-id="e18a6-133">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (Where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="e18a6-134">При нацеливании на платформу .NET Standard есть три основных варианта, выбор которых зависит от ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="e18a6-134">You have three primary options when targeting the .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="e18a6-135">Вы можете использовать версию .NET Standard по умолчанию, которая предоставляется шаблонами `netstandard1.4` и обеспечивает доступ к большинству API-интерфейсов .NET Standard, сохраняя совместимость с UWP, .NET Framework 4.6.1 и новой платформой .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="e18a6-135">You can use the default version of the .NET Standard supplied by templates - `netstandard1.4` - which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and the forthcoming .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="e18a6-136">Можно использовать более раннюю или более позднюю версию .NET Standard, изменив значение в узле `TargetFramework` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="e18a6-136">You can use a lower or higher version of the .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>
    
    <span data-ttu-id="e18a6-137">Версии .NET Standard обладают обратной совместимостью.</span><span class="sxs-lookup"><span data-stu-id="e18a6-137">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="e18a6-138">Это означает, что библиотеки `netstandard1.0` выполняются на платформах `netstandard1.1` и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e18a6-138">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="e18a6-139">Однако прямой совместимости нет: более ранние платформы .NET Standard не могут ссылаться на более поздние.</span><span class="sxs-lookup"><span data-stu-id="e18a6-139">However, there is no forward compatibility - lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="e18a6-140">Это значит, что библиотеки `netstandard1.0` не могут ссылаться на библиотеки, предназначенные для `netstandard1.1` или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e18a6-140">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="e18a6-141">Выберите версию Standard, которая предоставляет подходящее сочетание интерфейсов API и поддерживаемых платформ для ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="e18a6-141">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="e18a6-142">Сейчас рекомендуем использовать версию `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-142">We recommend `netstandard1.4` for now.</span></span>
    
3. <span data-ttu-id="e18a6-143">Если требуется нацеливание на .NET Framework версии 4.0 или более ранней или использование интерфейса API, доступного в .NET Framework, но не в .NET Standard (например, `System.Drawing`), прочитайте следующие подразделы, чтобы узнать, как осуществляется настройка для разных версий.</span><span class="sxs-lookup"><span data-stu-id="e18a6-143">If you want to target the .NET Framework versions 4.0 or below, or you wish to use an API available in the .NET Framework but not in the .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-the-net-framework"></a><span data-ttu-id="e18a6-144">Нацеливание на .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e18a6-144">How to target the .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="e18a6-145">В этих инструкциях предполагается, что на компьютере установлена платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-145">These instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="e18a6-146">Чтобы установить зависимости, обратитесь к разделу [Предварительные требования](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="e18a6-146">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="e18a6-147">Имейте в виду, что некоторые используемые здесь версии .NET Framework больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e18a6-147">Keep in mind that some of the .NET Framework versions used here are no longer in support.</span></span> <span data-ttu-id="e18a6-148">Сведения о неподдерживаемых версиях см. в статье [Вопросы и ответы о политике по срокам поддержки Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).</span><span class="sxs-lookup"><span data-stu-id="e18a6-148">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="e18a6-149">Чтобы охватить максимальное количество разработчиков и проектов, используйте .NET Framework 4.0 в качестве базовой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="e18a6-149">If you want to reach the maximum number of developers and projects, use the .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="e18a6-150">Для нацеливания на .NET Framework сначала необходимо использовать моникер целевой платформы (TFM), соответствующий версии .NET Framework, которая должна поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="e18a6-150">To target the .NET Framework, you will need to begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.7   --> net47
```

<span data-ttu-id="e18a6-151">Вставьте этот моникер целевой платформы в раздел `TargetFramework` файла проекта.</span><span class="sxs-lookup"><span data-stu-id="e18a6-151">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="e18a6-152">Например, вот как создать библиотеку, предназначенную для .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="e18a6-152">For example, here's how you would write a library which targets the .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="e18a6-153">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="e18a6-153">And that's it!</span></span> <span data-ttu-id="e18a6-154">Хотя эта библиотека компилируется только для .NET Framework 4, ее можно использовать в более поздних версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-154">Although this compiled only for the .NET Framework 4, you can use the library on newer versions of the .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="e18a6-155">Настройка для различных версий</span><span class="sxs-lookup"><span data-stu-id="e18a6-155">How to Multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="e18a6-156">В приведенных ниже инструкциях предполагается, что на компьютере установлена платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-156">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="e18a6-157">Сведения о зависимостях, которые необходимо установить, и о том, где их можно скачать, см. в разделе [Предварительные требования](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="e18a6-157">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="e18a6-158">Если проект поддерживает как .NET Framework, так и .NET Core, может потребоваться нацеливание на более старые версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-158">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="e18a6-159">В такой ситуации, если вам нужно применять более новые интерфейсы API и языковые конструкции для новых целевых платформ, используйте директивы `#if` в коде.</span><span class="sxs-lookup"><span data-stu-id="e18a6-159">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="e18a6-160">Кроме того, может потребоваться добавить разные пакеты и зависимости для каждой целевой платформы, чтобы включить различные интерфейсы API, необходимые в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="e18a6-160">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="e18a6-161">Предположим, имеется библиотека, выполняющая сетевые операции по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="e18a6-161">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="e18a6-162">Для .NET Standard и .NET Framework версии 4.5 или более поздней можно использовать класс `HttpClient` из пространства имен `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-162">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="e18a6-163">Однако в более ранних версиях .NET Framework нет класса `HttpClient`, поэтому вместо него можно использовать класс `WebClient` из пространства имен `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-163">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="e18a6-164">Файл проекта может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e18a6-164">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="e18a6-165">Вы заметите три основных изменения:</span><span class="sxs-lookup"><span data-stu-id="e18a6-165">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="e18a6-166">Узел `TargetFramework` был заменен на `TargetFrameworks`, внутри которого содержатся три моникера целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="e18a6-166">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="e18a6-167">Добавлен узел `<ItemGroup>` для целевой платформы `net40 `, который извлекает одну ссылку на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-167">There is an `<ItemGroup>` node for the `net40 ` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="e18a6-168">Добавлен узел `<ItemGroup>` для целевой платформы `net45`, который извлекает две ссылки на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e18a6-168">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="e18a6-169">Система сборки распознает следующие символы препроцессора, используемые в директивах `#if`:</span><span class="sxs-lookup"><span data-stu-id="e18a6-169">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="e18a6-170">Ниже приведен пример использования условной компиляции для каждого целевого объекта:</span><span class="sxs-lookup"><span data-stu-id="e18a6-170">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "http://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="e18a6-171">При сборке этого проекта с `dotnet build` вы увидите, что в папке `bin/` появились три каталога:</span><span class="sxs-lookup"><span data-stu-id="e18a6-171">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="e18a6-172">Каждый из них содержит файлы `.dll` для соответствующего целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="e18a6-172">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="e18a6-173">Тестирование библиотек в .NET Core</span><span class="sxs-lookup"><span data-stu-id="e18a6-173">How to test libraries on .NET Core</span></span>

<span data-ttu-id="e18a6-174">Необходимо иметь возможность тестирования проектов на различных платформах.</span><span class="sxs-lookup"><span data-stu-id="e18a6-174">It's important to be able to test across platforms.</span></span> <span data-ttu-id="e18a6-175">Вы можете использовать [xUnit](http://xunit.github.io/) или MSTest без дополнительной настройки.</span><span class="sxs-lookup"><span data-stu-id="e18a6-175">You can use either [xUnit](http://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="e18a6-176">Обе платформы тестирования идеально подходят для модульного тестирования библиотеки в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e18a6-176">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="e18a6-177">Настройка тестовых проектов для решения зависит от [его структуры](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="e18a6-177">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="e18a6-178">В следующем примере предполагается, что каталог с тестами и каталог с исходным кодом находятся в одном и том же каталоге верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="e18a6-178">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="e18a6-179">В этом примере используются некоторые [команды интерфейса командной строки .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="e18a6-179">This uses some [.NET Core CLI commands](../tools/index.md).</span></span> <span data-ttu-id="e18a6-180">Дополнительные сведения см. в разделах [dotnet new](../tools/dotnet-new.md) и [dotnet sln](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="e18a6-180">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="e18a6-181">Настройте решение.</span><span class="sxs-lookup"><span data-stu-id="e18a6-181">Set up your solution.</span></span> <span data-ttu-id="e18a6-182">Это можно сделать с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="e18a6-182">You can do so with the following commands:</span></span>

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="e18a6-183">Эти команды создадут проекты и объединят их в решение.</span><span class="sxs-lookup"><span data-stu-id="e18a6-183">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="e18a6-184">Ваш каталог для `SolutionWithSrcAndTest` должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e18a6-184">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="e18a6-185">Перейдите в каталог тестового проекта и добавьте ссылку на `MyProject.Test` из `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-185">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="e18a6-186">Восстановите пакеты и соберите проекты:</span><span class="sxs-lookup"><span data-stu-id="e18a6-186">Restore packages and build projects:</span></span>

   ```bash
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

1. <span data-ttu-id="e18a6-187">Убедитесь, что xUnit запущен, выполнив команду `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-187">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="e18a6-188">Если вы решили использовать MSTest, запустите средство запуска консоли MSTest вместо xUnit.</span><span class="sxs-lookup"><span data-stu-id="e18a6-188">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>
    
<span data-ttu-id="e18a6-189">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="e18a6-189">And that's it!</span></span> <span data-ttu-id="e18a6-190">Теперь вы можете протестировать библиотеку для всех платформ с помощью средств командной строки.</span><span class="sxs-lookup"><span data-stu-id="e18a6-190">You can now test your library across all platforms using command line tools.</span></span> <span data-ttu-id="e18a6-191">Теперь, когда все настроено, протестировать библиотеку очень легко:</span><span class="sxs-lookup"><span data-stu-id="e18a6-191">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="e18a6-192">Внесите изменения в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e18a6-192">Make changes to your library.</span></span>
1. <span data-ttu-id="e18a6-193">Выполните тесты в тестовом каталоге из командной строки с помощью команды `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-193">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="e18a6-194">При вызове команды `dotnet test` будет автоматически выполнена повторная сборка кода.</span><span class="sxs-lookup"><span data-stu-id="e18a6-194">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="e18a6-195">Использование нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="e18a6-195">How to use multiple projects</span></span>

<span data-ttu-id="e18a6-196">В случае с более крупными библиотеками, как правило, требуется реализовывать функциональность в разных проектах.</span><span class="sxs-lookup"><span data-stu-id="e18a6-196">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="e18a6-197">Представим, что необходимо создать библиотеку, которую можно использовать в идиоматичном коде на языках C# и F#.</span><span class="sxs-lookup"><span data-stu-id="e18a6-197">Imagine you wished to build a library which could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="e18a6-198">Это означает, что библиотека будет использоваться способами, естественными для языков C# и F#.</span><span class="sxs-lookup"><span data-stu-id="e18a6-198">That would mean that consumers of your library consume them in ways which are natural to C# or F#.</span></span> <span data-ttu-id="e18a6-199">Например, в C# можно использовать библиотеку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e18a6-199">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="e18a6-200">В F# это может выглядеть так.</span><span class="sxs-lookup"><span data-stu-id="e18a6-200">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="e18a6-201">Подобные сценарии использования предполагают, что интерфейсы API, к которым осуществляется доступ, должны иметь разную структуру для C# и F#.</span><span class="sxs-lookup"><span data-stu-id="e18a6-201">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="e18a6-202">Стандартным подходом к решению этой задачи является факторинг всей логики библиотеки в базовом проекте и определение в проектах C# и F# уровней API, которые вызывают этот базовый проект.</span><span class="sxs-lookup"><span data-stu-id="e18a6-202">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="e18a6-203">Далее в этом разделе будут использоваться следующие имена:</span><span class="sxs-lookup"><span data-stu-id="e18a6-203">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="e18a6-204">**AwesomeLibrary.Core** — базовый проект, содержащий всю логику библиотеки;</span><span class="sxs-lookup"><span data-stu-id="e18a6-204">**AwesomeLibrary.Core** - A core project which contains all logic for the library</span></span>
* <span data-ttu-id="e18a6-205">**AwesomeLibrary.CSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке C#</span><span class="sxs-lookup"><span data-stu-id="e18a6-205">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="e18a6-206">**AwesomeLibrary.FSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке F#</span><span class="sxs-lookup"><span data-stu-id="e18a6-206">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="e18a6-207">Чтобы получить ту же структуру каталогов, что и в этом руководстве, выполните следующие команды в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="e18a6-207">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```console
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang F#
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="e18a6-208">Эти команды добавят три указанные выше проекта и файл решения, который связывает их вместе.</span><span class="sxs-lookup"><span data-stu-id="e18a6-208">This will add the three projects above and a solution file which links them together.</span></span> <span data-ttu-id="e18a6-209">Создание файла решения и связывание проектов позволит вам собирать и восстанавливать проекты из верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="e18a6-209">Creating the solution file and linking projects will allow you to restore and build projects from a top-level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="e18a6-210">Ссылки проектов на проекты</span><span class="sxs-lookup"><span data-stu-id="e18a6-210">Project-to-project referencing</span></span>

<span data-ttu-id="e18a6-211">Ссылку на проект лучше всего добавить с помощью интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e18a6-211">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="e18a6-212">Из каталогов проекта **AwesomeLibrary.CSharp** и **AwesomeLibrary.FSharp** выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e18a6-212">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```console
$ dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="e18a6-213">Теперь файлы **AwesomeLibrary.CSharp** и **AwesomeLibrary.FSharp** будут ссылаться на **AwesomeLibrary.Core** в качестве целевого объекта `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="e18a6-213">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="e18a6-214">Чтобы это проверить, просмотрите файлы проектов, и вы увидите в них следующий код:</span><span class="sxs-lookup"><span data-stu-id="e18a6-214">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="e18a6-215">Если вы не хотите использовать интерфейс командной строки .NET Core, можете добавить этот раздел в каждый файл проекта вручную.</span><span class="sxs-lookup"><span data-stu-id="e18a6-215">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="e18a6-216">Структурирование решения</span><span class="sxs-lookup"><span data-stu-id="e18a6-216">Structuring a solution</span></span>

<span data-ttu-id="e18a6-217">Еще один важный аспект решений с несколькими проектами — правильное формирование общей структуры.</span><span class="sxs-lookup"><span data-stu-id="e18a6-217">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="e18a6-218">Код можно упорядочить так, как вам удобно. Если каждый проект связан с файлом решения с помощью `dotnet sln add`, вы сможете запускать команды `dotnet restore` и `dotnet build` на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="e18a6-218">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
