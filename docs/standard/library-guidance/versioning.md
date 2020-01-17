---
title: Управление версиями и библиотеки .NET
description: Рекомендации по использованию системы управления версиями для библиотек .NET.
ms.date: 12/10/2018
ms.openlocfilehash: 8ed3217e39b1fe0f330a650ec72cda224866e207
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706417"
---
# <a name="versioning"></a><span data-ttu-id="02f68-103">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="02f68-103">Versioning</span></span>

<span data-ttu-id="02f68-104">Разработка библиотек программного обеспечения редко завершается версией 1.0.</span><span class="sxs-lookup"><span data-stu-id="02f68-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="02f68-105">Хорошая библиотека постоянно развивается: появляются новые функции, исправляются ошибки и повышается производительность.</span><span class="sxs-lookup"><span data-stu-id="02f68-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="02f68-106">Очень важно правильно выпускать новые версии библиотеки .NET, расширяя ее возможности и не допуская появления проблем для уже существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="02f68-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="02f68-107">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="02f68-107">Breaking changes</span></span>

<span data-ttu-id="02f68-108">См. сведения об [оценке критических изменений между версиями](./breaking-changes.md).</span><span class="sxs-lookup"><span data-stu-id="02f68-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="02f68-109">Номера версий</span><span class="sxs-lookup"><span data-stu-id="02f68-109">Version numbers</span></span>

<span data-ttu-id="02f68-110">Для библиотеки .NET версию можно указать разными способами.</span><span class="sxs-lookup"><span data-stu-id="02f68-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="02f68-111">Вот несколько наиболее важных версий:</span><span class="sxs-lookup"><span data-stu-id="02f68-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="02f68-112">Версия пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="02f68-112">NuGet package version</span></span>

<span data-ttu-id="02f68-113">[Версия пакета NuGet](/nuget/reference/package-versioning) отображается на сайте NuGet.org в диспетчере пакетов Visual Studio NuGet. Она добавляется к исходному коду при использовании пакета.</span><span class="sxs-lookup"><span data-stu-id="02f68-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="02f68-114">Именно версию пакета NuGet чаще всего будут видеть пользователи и именно ее они будут считать версией используемой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="02f68-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="02f68-115">Версия пакета NuGet используется только в пределах NuGet и никак не влияет на поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02f68-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="02f68-116">Идентификатор пакета NuGet в сочетании с версией пакета NuGet используется для идентификации пакета в NuGet.</span><span class="sxs-lookup"><span data-stu-id="02f68-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="02f68-117">Например, `Newtonsoft.Json` + `11.0.2`.</span><span class="sxs-lookup"><span data-stu-id="02f68-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="02f68-118">Пакет с суффиксом обозначает пакет предварительной версии, и для него используются специальные правила, благодаря которым он идеально подходит для тестирования.</span><span class="sxs-lookup"><span data-stu-id="02f68-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="02f68-119">См. с сведения о [пакетах предварительной версии](./nuget.md#pre-release-packages).</span><span class="sxs-lookup"><span data-stu-id="02f68-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="02f68-120">Так как версия пакета NuGet встречается разработчикам чаще всего, мы рекомендуем обновлять ее с использованием [Семантического версионирования](https://semver.org/) (SemVer).</span><span class="sxs-lookup"><span data-stu-id="02f68-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="02f68-121">SemVer указывает на значимость изменений, реализованных в очередном выпуске, помогая разработчикам правильно выбрать версию для использования.</span><span class="sxs-lookup"><span data-stu-id="02f68-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="02f68-122">Например, переход от версии `1.0` к `2.0` указывает на наличие потенциальных критических изменений.</span><span class="sxs-lookup"><span data-stu-id="02f68-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="02f68-123">**✔️ CONSIDER** Использование [SemVer 2.0.0](https://semver.org/) для управления версиями пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="02f68-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="02f68-124">**✔️ РЕКОМЕНДУЕТСЯ.** Используйте версию пакета NuGet в общедоступной документации, так как именно этот номер версии пользователи будут видеть чаще всего.</span><span class="sxs-lookup"><span data-stu-id="02f68-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="02f68-125">**✔️ РЕКОМЕНДУЕТСЯ.** Добавьте суффикс предварительной версии при выпуске нестабильной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="02f68-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="02f68-126">Чтобы использовать пакеты предварительных версий, пользователи должны явно согласиться с тем, что работа над пакетом еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="02f68-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="02f68-127">Версия сборки</span><span class="sxs-lookup"><span data-stu-id="02f68-127">Assembly version</span></span>

<span data-ttu-id="02f68-128">Версия сборки используется средой CLR во время выполнения для выбора загружаемой версии сборки.</span><span class="sxs-lookup"><span data-stu-id="02f68-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="02f68-129">Выбор сборки через систему управления версиями применяется только к сборкам со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="02f68-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="02f68-130">Среда CLR Windows для .NET Framework при загрузке сборки со строгими именами требует точного совпадения номера.</span><span class="sxs-lookup"><span data-stu-id="02f68-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="02f68-131">Предположим, что `Libary1, Version=1.0.0.0` компилируется со ссылкой на `Newtonsoft.Json, Version=11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="02f68-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="02f68-132">Тогда .NET Framework будет загружать только версию `11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="02f68-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="02f68-133">Чтобы загрузить во время выполнения другую версию, необходимо добавить переадресацию привязок в файл конфигурации приложения .NET.</span><span class="sxs-lookup"><span data-stu-id="02f68-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="02f68-134">Использование строгого именования в сочетании с версией сборки позволяет организовать [строгую загрузку версий сборок](../assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="02f68-134">Strong naming combined with assembly version enables [strict assembly version loading](../assembly/versioning.md).</span></span> <span data-ttu-id="02f68-135">Хотя строгое именование библиотек имеет ряд преимуществ, оно часто вызывает исключения времени выполнения, если не удается найти точную версию сборки. Для устранения таких проблем требуется [переадресация привязок](../../framework/configure-apps/redirect-assembly-versions.md) в `app.config`/`web.config`.</span><span class="sxs-lookup"><span data-stu-id="02f68-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="02f68-136">Загрузка сборок в .NET Core стала менее строгой, и среда CLR в .NET Core автоматически загружает во время выполнения сборки с более поздней версией.</span><span class="sxs-lookup"><span data-stu-id="02f68-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="02f68-137">**✔️ ДОПУСТИМО.** Вы можете указывать в AssemblyVersion только основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="02f68-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="02f68-138">Например, для библиотек версий 1.0 и 1.0.1 можно указать одинаковое значение AssemblyVersion `1.0.0.0`, а для библиотеки 2.0 изменить AssemblyVersion на `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="02f68-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="02f68-139">Если версия сборки меняется редко, потребуется меньше переадресаций привязок.</span><span class="sxs-lookup"><span data-stu-id="02f68-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="02f68-140">**✔️ ДОПУСТИМО.** Вы можете синхронизировать основной номер версии AssemblyVersion и версию пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="02f68-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="02f68-141">Номер AssemblyVersion включается в некоторые информационные сообщения для пользователей, например в составе имени сборки и имени типа сборки в сообщениях об исключениях.</span><span class="sxs-lookup"><span data-stu-id="02f68-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="02f68-142">Сохранение связи между этими версиями позволит разработчикам лучше понимать, какую версию они используют.</span><span class="sxs-lookup"><span data-stu-id="02f68-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="02f68-143">**❌ НЕЛЬЗЯ**. Не используйте фиксированное значение AssemblyVersion.</span><span class="sxs-lookup"><span data-stu-id="02f68-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="02f68-144">Конечно же, отсутствие изменений в AssemblyVersion позволит избежать переадресации привязок, запрещая устанавливать более одной версии сборки в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="02f68-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="02f68-145">Кроме того, приложения со ссылками на такую сборку в глобальном кэше сборок не смогут работать, если другое приложение загрузит в глобальный кэш сборок новую версию сборки с критическими изменениями.</span><span class="sxs-lookup"><span data-stu-id="02f68-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="02f68-146">Версия файла сборки</span><span class="sxs-lookup"><span data-stu-id="02f68-146">Assembly file version</span></span>

<span data-ttu-id="02f68-147">Версия файла сборки используется для отображения версии файла в ОС Windows и никак не влияет на поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02f68-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="02f68-148">Настройка этой версии является необязательной.</span><span class="sxs-lookup"><span data-stu-id="02f68-148">Setting this version is optional.</span></span> <span data-ttu-id="02f68-149">Она отображается в диалоговом окне "Свойства файла" в проводнике Windows:</span><span class="sxs-lookup"><span data-stu-id="02f68-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="02f68-150">![Проводник](./media/versioning/win-properties.png "Проводник")</span><span class="sxs-lookup"><span data-stu-id="02f68-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

<span data-ttu-id="02f68-151">**✔️ ДОПУСТИМО.** Вы можете использовать номер сборки непрерывной интеграции в качестве номера редакции AssemblyFileVersion.</span><span class="sxs-lookup"><span data-stu-id="02f68-151">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="02f68-152">Например, если вы создаете версию проекта 1.0.0, а номер сборки непрерывной интеграции имеет значение 99, параметр AssemblyFileVersion получит значение 1.0.0.99.</span><span class="sxs-lookup"><span data-stu-id="02f68-152">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

<span data-ttu-id="02f68-153">**✔️ ИСПОЛЬЗУЙТЕ** формат `Major.Minor.Build.Revision` для версии файла.</span><span class="sxs-lookup"><span data-stu-id="02f68-153">**✔️ DO** use the format `Major.Minor.Build.Revision` for file version.</span></span>

> <span data-ttu-id="02f68-154">Версия файла никогда не применяется в .NET, но [в Windows ожидается версия файла](/windows/desktop/menurc/versioninfo-resource) в формате `Major.Minor.Build.Revision`.</span><span class="sxs-lookup"><span data-stu-id="02f68-154">While the file version is never used by .NET, [Windows expects the file version](/windows/desktop/menurc/versioninfo-resource) to be in the `Major.Minor.Build.Revision` format.</span></span> <span data-ttu-id="02f68-155">Если версия не соответствует этому формату, появляется предупреждение.</span><span class="sxs-lookup"><span data-stu-id="02f68-155">A warning is raised if the version doesn't follow this format.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="02f68-156">Информационная версия сборки</span><span class="sxs-lookup"><span data-stu-id="02f68-156">Assembly informational version</span></span>

<span data-ttu-id="02f68-157">Информационная версия сборки используется для сохранения дополнительных сведений о версии и никак не влияет на поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="02f68-157">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="02f68-158">Настройка этой версии является необязательной.</span><span class="sxs-lookup"><span data-stu-id="02f68-158">Setting this version is optional.</span></span> <span data-ttu-id="02f68-159">Если вы используете SourceLink, это значение при сборке составляется из номера версии пакета NuGet и номера в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="02f68-159">If you're using Source Link, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="02f68-160">Например, `1.0.0-beta1+204ff0a` включает хэш фиксации для исходного кода, из которого построена сборка.</span><span class="sxs-lookup"><span data-stu-id="02f68-160">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="02f68-161">Дополнительные сведения см. в разделе [Ссылка на источник](./sourcelink.md).</span><span class="sxs-lookup"><span data-stu-id="02f68-161">For more information, see [Source Link](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

> [!NOTE]
> <span data-ttu-id="02f68-162">В более ранних версиях Visual Studio отображается предупреждение сборки, если эта версия не соответствует формату `Major.Minor.Build.Revision`.</span><span class="sxs-lookup"><span data-stu-id="02f68-162">Older versions of Visual Studio raise a build warning if this version doesn't follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="02f68-163">Его можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="02f68-163">The warning can be safely ignored.</span></span>

<span data-ttu-id="02f68-164">**❌ НЕЖЕЛАТЕЛЬНО**. Не указывайте самостоятельно информационную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="02f68-164">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="02f68-165">Разрешите SourceLink автоматически создавать этот номер версии из метаданных NuGet и системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="02f68-165">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="02f68-166">[Назад](publish-nuget-package.md)
>[Вперед](breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="02f68-166">[Previous](publish-nuget-package.md)
[Next](breaking-changes.md)</span></span>
