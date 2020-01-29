---
title: Обзор global.json
description: Узнайте, как использовать файл global.json, чтобы задать версию пакета SDK для .NET Core при выполнении команд .NET Core CLI.
ms.date: 01/14/2020
ms.custom: updateeachrelease
ms.openlocfilehash: f02c9129a707ddddb2c5e1975b75cc35abc5cd55
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733976"
---
# <a name="globaljson-overview"></a><span data-ttu-id="333c2-103">Обзор global.json</span><span class="sxs-lookup"><span data-stu-id="333c2-103">global.json overview</span></span>

<span data-ttu-id="333c2-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="333c2-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="333c2-105">С помощью файла *global.json* можно определить, какая версия пакета SDK для .NET Core используется при выполнении команд .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="333c2-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="333c2-106">Выбор пакета SDK для .NET Core не зависит от указания целевой среды выполнения проекта.</span><span class="sxs-lookup"><span data-stu-id="333c2-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="333c2-107">Версия пакета SDK для .NET Core указывает, какие версии средств .NET Core CLI используются.</span><span class="sxs-lookup"><span data-stu-id="333c2-107">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span>

<span data-ttu-id="333c2-108">Как правило, необходимо использовать последнюю версию средств пакета SDK, поэтому вам нужен файл *global.json*.</span><span class="sxs-lookup"><span data-stu-id="333c2-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="333c2-109">В некоторых сложных сценариях может потребоваться управление версией средств пакета SDK, и в этой статье объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="333c2-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="333c2-110">Дополнительные сведения о том, как вместо этого указать среду выполнения, см. в разделе [Целевые платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="333c2-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="333c2-111">Пакет SDK для .NET Core ищет файл *global.json* в текущем рабочем каталоге (который не обязательно совпадает с каталогом проекта) или в одном из его родительских каталогов.</span><span class="sxs-lookup"><span data-stu-id="333c2-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="333c2-112">Схема файла global.json</span><span class="sxs-lookup"><span data-stu-id="333c2-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="333c2-113">sdk</span><span class="sxs-lookup"><span data-stu-id="333c2-113">sdk</span></span>

<span data-ttu-id="333c2-114">Тип: `object`</span><span class="sxs-lookup"><span data-stu-id="333c2-114">Type: `object`</span></span>

<span data-ttu-id="333c2-115">Указывает сведения о пакете SDK для .NET Core для выбора.</span><span class="sxs-lookup"><span data-stu-id="333c2-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="333c2-116">version</span><span class="sxs-lookup"><span data-stu-id="333c2-116">version</span></span>

- <span data-ttu-id="333c2-117">Тип: `string`</span><span class="sxs-lookup"><span data-stu-id="333c2-117">Type: `string`</span></span>

- <span data-ttu-id="333c2-118">Доступно начиная с пакета SDK для .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="333c2-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="333c2-119">Версия пакета SDK для .NET Core для использования.</span><span class="sxs-lookup"><span data-stu-id="333c2-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="333c2-120">Это поле:</span><span class="sxs-lookup"><span data-stu-id="333c2-120">This field:</span></span>

- <span data-ttu-id="333c2-121">Не поддерживает подстановочные знаки, то есть необходимо указать полный номер версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="333c2-122">Не поддерживает диапазон версий.</span><span class="sxs-lookup"><span data-stu-id="333c2-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="333c2-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="333c2-123">allowPrerelease</span></span>

- <span data-ttu-id="333c2-124">Тип: `boolean`</span><span class="sxs-lookup"><span data-stu-id="333c2-124">Type: `boolean`</span></span>

- <span data-ttu-id="333c2-125">Доступно начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="333c2-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="333c2-126">Указывает, должен ли сопоставитель пакетов SDK учитывать предварительные версии при выборе версии пакета SDK, которую следует использовать.</span><span class="sxs-lookup"><span data-stu-id="333c2-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="333c2-127">Если это значение не задано явно, значение по умолчанию зависит от того, работаете ли вы в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="333c2-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="333c2-128">Если вы **не** работаете в Visual Studio, значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="333c2-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="333c2-129">Если работаете в Visual Studio, используется запрошенное состояние предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="333c2-130">То есть если вы используете предварительную версию Visual Studio или включили параметр **Использовать предварительные версии пакета SDK для .NET Core** (в разделе **Сервис** > **Параметры** > **Среда** > **Функции предварительной версии**), значением по умолчанию будет `true`; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="333c2-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="333c2-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="333c2-131">rollForward</span></span>

- <span data-ttu-id="333c2-132">Тип: `string`</span><span class="sxs-lookup"><span data-stu-id="333c2-132">Type: `string`</span></span>

- <span data-ttu-id="333c2-133">Доступно начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="333c2-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="333c2-134">Политика наката, используемая при выборе версии пакета SDK (либо в качестве резервной, если определенная версия пакета SDK отсутствует, либо в качестве директивы для использования более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="333c2-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="333c2-135">[Версия](#version) должна быть указана со значением `rollForward`, если только вы не настраиваете ее равной `latestMajor`.</span><span class="sxs-lookup"><span data-stu-id="333c2-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>

<span data-ttu-id="333c2-136">Для понимания доступных политик и их поведения примите во внимание следующие определения для версии пакета SDK в формате `x.y.znn`:</span><span class="sxs-lookup"><span data-stu-id="333c2-136">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="333c2-137">`x` — основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-137">`x` is the major version.</span></span>
- <span data-ttu-id="333c2-138">`y` — дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-138">`y` is the minor version.</span></span>
- <span data-ttu-id="333c2-139">`z` — набор возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-139">`z` is the feature band.</span></span>
- <span data-ttu-id="333c2-140">`nn` — версия исправления.</span><span class="sxs-lookup"><span data-stu-id="333c2-140">`nn` is the patch version.</span></span>

<span data-ttu-id="333c2-141">В следующей таблице описаны возможные значения параметра `rollForward`.</span><span class="sxs-lookup"><span data-stu-id="333c2-141">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="333c2-142">Значение</span><span class="sxs-lookup"><span data-stu-id="333c2-142">Value</span></span>         | <span data-ttu-id="333c2-143">Поведение</span><span class="sxs-lookup"><span data-stu-id="333c2-143">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="333c2-144">Использует указанную версию.</span><span class="sxs-lookup"><span data-stu-id="333c2-144">Uses the specified version.</span></span> <br> <span data-ttu-id="333c2-145">Если не найдено, выполняет накат до последнего уровня обновления.</span><span class="sxs-lookup"><span data-stu-id="333c2-145">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="333c2-146">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-146">If not found, fails.</span></span> <br><br> <span data-ttu-id="333c2-147">Это значение является устаревшим поведением по сравнению с предыдущими версиями пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="333c2-147">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="333c2-148">Использует последний уровень обновления для указанного основного номера версии, дополнительного номера версии и набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-148">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="333c2-149">Если не найдено, выполняет накат до следующего набора возможностей более высокого уровня в пределах одного и того же основного или дополнительного номера версии и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-149">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-150">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-150">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="333c2-151">Использует последний уровень обновления для указанного основного номера версии, дополнительного номера версии и набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-151">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="333c2-152">Если не найдено, выполняет накат до следующего набора возможностей более высокого уровня в пределах одного и того же основного или дополнительного номера версии и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-152">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-153">Если не найдено, выполняет накат до следующего основного номера версии и набора возможностей более высокого уровня в пределах одного и того же основного номера версии и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-153">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-154">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-154">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="333c2-155">Использует последний уровень обновления для указанного основного номера версии, дополнительного номера версии и набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-155">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="333c2-156">Если не найдено, выполняет накат до следующего набора возможностей более высокого уровня в пределах одного и того же основного или дополнительного номера версии и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-156">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-157">Если не найдено, выполняет накат до следующего основного номера версии и набора возможностей более высокого уровня в пределах одного и того же основного номера версии и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-157">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-158">Если не найдено, выполняет накат до следующего основного номера версии, дополнительного номера версии и набора возможностей более высокого уровня и использует последний уровень обновления для этого набора возможностей.</span><span class="sxs-lookup"><span data-stu-id="333c2-158">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="333c2-159">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-159">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="333c2-160">Использует последний установленный уровень обновления, соответствующий запрошенному основному номеру версии, дополнительному номеру версии и набору возможностей с уровнем обновления, который соответствует указанному значению или превышает его.</span><span class="sxs-lookup"><span data-stu-id="333c2-160">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="333c2-161">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-161">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="333c2-162">Использует наивысший установленный набор возможностей и уровень обновления, соответствующий запрошенному основному номеру версии и дополнительному номеру версии с набором возможностей, который соответствует указанному значению или превышает его.</span><span class="sxs-lookup"><span data-stu-id="333c2-162">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="333c2-163">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-163">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="333c2-164">Использует наивысший установленный основной номер версии, набор возможностей и уровень обновления, соответствующий запрошенному основному номеру версии с дополнительным номером версии, который соответствует указанному значению или превышает его.</span><span class="sxs-lookup"><span data-stu-id="333c2-164">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="333c2-165">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-165">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="333c2-166">Использует наивысший установленный пакет SDK для .NET Core с основным номером версии, который соответствует указанному значению или превышает его.</span><span class="sxs-lookup"><span data-stu-id="333c2-166">Uses the highest installed .NET Core SDK with a major that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="333c2-167">Если не найдено, происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="333c2-167">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="333c2-168">Накат не выполняется.</span><span class="sxs-lookup"><span data-stu-id="333c2-168">Doesn't roll forward.</span></span> <span data-ttu-id="333c2-169">Требуется точное соответствие.</span><span class="sxs-lookup"><span data-stu-id="333c2-169">Exact match required.</span></span> |

## <a name="examples"></a><span data-ttu-id="333c2-170">Примеры</span><span class="sxs-lookup"><span data-stu-id="333c2-170">Examples</span></span>

<span data-ttu-id="333c2-171">В следующем примере показано, как не использовать предварительные версии:</span><span class="sxs-lookup"><span data-stu-id="333c2-171">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="333c2-172">В следующем примере показано, как использовать наивысший установленный номер версии, который соответствует указанной версии или больше нее:</span><span class="sxs-lookup"><span data-stu-id="333c2-172">The following example shows how to use the highest version installed that is greater or equal than the specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="333c2-173">В следующем примере показано, как использовать точную указанную версию:</span><span class="sxs-lookup"><span data-stu-id="333c2-173">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="333c2-174">В следующем примере показано, как использовать наивысшую версию обновления, установленную для конкретной версии (в формате 3.1.1xx):</span><span class="sxs-lookup"><span data-stu-id="333c2-174">The following example shows how to use the highest patch version installed of a specific version (in the form, 3.1.1xx):</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="333c2-175">global.json и .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="333c2-175">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="333c2-176">Полезно знать, какие версии пакета SDK установлены на компьютере, чтобы задать их в файле *global.json*.</span><span class="sxs-lookup"><span data-stu-id="333c2-176">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="333c2-177">Дополнительные сведения о том, как это сделать, см. в разделе [Проверка того, установлена ли платформа .NET Core](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="333c2-177">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="333c2-178">Чтобы установить дополнительные версии пакета SDK для .NET Core на компьютере, посетите страницу [скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="333c2-178">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="333c2-179">Вы можете создать новый файл *global.json* в текущем каталоге, выполнив команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="333c2-179">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="333c2-180">Правила сопоставления</span><span class="sxs-lookup"><span data-stu-id="333c2-180">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="333c2-181">Правила сопоставления определяются точкой входа `dotnet.exe`, которая является общей для всех установленных сред выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="333c2-181">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="333c2-182">Правила сопоставления для последней установленной версии среды выполнения .NET Core используются при параллельной установке сразу нескольких сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="333c2-182">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side.</span></span>

## <a name="net-core-3xtabnetcore3x"></a>[<span data-ttu-id="333c2-183">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="333c2-183">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="333c2-184">Начиная с .NET Core 3.0 при определении версии пакета SDK для использования применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="333c2-184">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="333c2-185">Если файл *global.json* не найден или в файле *global.json* не указаны версия пакета SDK или значение `allowPrerelease`, используется наивысшая версия пакета SDK (эквивалентная заданию значения `rollForward` для параметра `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="333c2-185">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="333c2-186">Необходимость учитывать предварительные версии пакета SDK зависит от того, как вызывается `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="333c2-186">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="333c2-187">Если вы **не** работаете в Visual Studio, учитываются предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-187">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="333c2-188">Если работаете в Visual Studio, используется запрошенное состояние предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-188">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="333c2-189">То есть если вы используете предварительную версию Visual Studio или включили параметр **Использовать предварительные версии пакета SDK для .NET Core** (в разделе **Сервис** > **Параметры** > **Среда** > **Функции предварительной версии**), учитываются предварительные версии; в противном случае учитываются только выпущенные версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-189">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="333c2-190">Если найден файл *global.json*, в котором не указана версия пакета SDK, но указано значение `allowPrerelease`, используется наивысшая версия пакета SDK (аналогично заданию значения `rollForward` для параметра `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="333c2-190">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="333c2-191">На то, может ли последняя версия пакета SDK выпускаться или быть предварительным выпуском, влияет значение `allowPrerelease`.</span><span class="sxs-lookup"><span data-stu-id="333c2-191">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="333c2-192">`true` указывает на то, что предварительные версии учитываются. `false` указывает на то, что учитываются только выпущенные версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-192">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="333c2-193">Если файл *global.json* найден и в нем указана версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="333c2-193">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="333c2-194">Если значение `rollFoward` не задано, в качестве политики `rollForward` по умолчанию используется `latestPatch`.</span><span class="sxs-lookup"><span data-stu-id="333c2-194">If no `rollFoward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="333c2-195">В противном случае проверьте каждое значение и их поведение в разделе [rollForward](#rollforward).</span><span class="sxs-lookup"><span data-stu-id="333c2-195">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="333c2-196">Сведения о том, учитываются ли предварительные версии и каково поведение по умолчанию, если параметр `allowPrerelease` не задан, представлены в разделе [allowPrerelease](#allowprerelease).</span><span class="sxs-lookup"><span data-stu-id="333c2-196">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="333c2-197">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="333c2-197">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="333c2-198">В пакете SDK для .NET Core 2 при определении версии пакета SDK для использования применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="333c2-198">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="333c2-199">Если файл *global.json* не найден или в файле *global.json* не указана версия пакета SDK, используется последняя установленная версия пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="333c2-199">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="333c2-200">Последняя версия пакета SDK может быть обычным или предварительным выпуском — выбирается наибольший номер версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-200">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="333c2-201">Если в файле *global.json* указана версия пакета SDK:</span><span class="sxs-lookup"><span data-stu-id="333c2-201">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="333c2-202">Если указанная версия пакета SDK найдена на компьютере, используется именно эта версия.</span><span class="sxs-lookup"><span data-stu-id="333c2-202">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="333c2-203">Если указанная версия пакета SDK не найдена на компьютере, используется последняя установленная **версия исправления** этой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="333c2-203">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="333c2-204">Последняя установленная **версия обновления** для пакета SDK может быть обычным или предварительным выпуском — используется наибольший номер версии.</span><span class="sxs-lookup"><span data-stu-id="333c2-204">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="333c2-205">В .NET Core 2.1 и более поздних версиях **версии исправления** ниже указанной **версии исправления** не учитываются при выборе пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="333c2-205">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="333c2-206">Если указанная версия пакета SDK и соответствующая **версия исправления** пакета SDK не найдена, выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="333c2-206">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="333c2-207">Версия пакета SDK состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="333c2-207">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="333c2-208">**Главный выпуск** пакета SDK для .NET Core обозначен первой цифрой (`x`) в последней части номера (`xyz`) для версии пакета SDK 2.1.100 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="333c2-208">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="333c2-209">Как правило, пакет SDK для .NET Core имеет более короткий цикл выпуска, чем .NET Core.</span><span class="sxs-lookup"><span data-stu-id="333c2-209">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="333c2-210">**Версия исправления** обозначена двумя последними цифрами (`yz`) в последней части номера (`xyz`) для версии пакета SDK 2.1.100 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="333c2-210">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="333c2-211">Например, если вы указываете `2.1.300` в качестве версии пакета SDK, ищется пакет SDK до версии `2.1.399`, но `2.1.400` не считается версией исправления для `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="333c2-211">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="333c2-212">Версии пакета SDK для .NET Core с `2.1.100` по `2.1.201` были выпущены во время перехода между схемами номеров версий и некорректно обрабатывают нотацию `xyz`.</span><span class="sxs-lookup"><span data-stu-id="333c2-212">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="333c2-213">Если вы указываете эти версии в файле *global.json*, мы рекомендуем убедиться, что указанные версии установлены на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="333c2-213">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="333c2-214">Устранение неполадок с оповещениями сборки</span><span class="sxs-lookup"><span data-stu-id="333c2-214">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="333c2-215">Вы работаете с предварительной версией пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="333c2-215">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="333c2-216">Версию пакета SDK можно указать в файле global.json в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="333c2-216">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="333c2-217">Дополнительные сведения см. на странице <https://go.microsoft.com/fwlink/?linkid=869452></span><span class="sxs-lookup"><span data-stu-id="333c2-217">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="333c2-218">Это предупреждение означает, что проект был скомпилирован с использованием предварительной версии пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="333c2-218">This warning indicates that your project was compiled using a prerelease version of the .NET Core SDK.</span></span> <span data-ttu-id="333c2-219">Версии пакета SDK для .NET Core имеют гарантированное качество.</span><span class="sxs-lookup"><span data-stu-id="333c2-219">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="333c2-220">Однако если вы не хотите использовать предварительную версию, ознакомьтесь с различными стратегиями, которые можно применять в отношении пакета SDK для .NET Core 3.0 или более поздней версии, обратившись к разделу [allowPrerelease](#allowprerelease).</span><span class="sxs-lookup"><span data-stu-id="333c2-220">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="333c2-221">Для компьютеров, на которые никогда не устанавливалась среда выполнения .NET Core 3.0 или более поздней версии или пакет SDK, необходимо создать файл *global.json* и указать точную версию, которую требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="333c2-221">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

> [!WARNING]
> <span data-ttu-id="333c2-222">Запускаемый проект '{startupProject}' нацелен на версию платформы '.NETCoreApp' '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="333c2-222">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="333c2-223">Эта версия средств командной строки .NET Entity Framework Core поддерживает только версию 2.0 или более позднюю.</span><span class="sxs-lookup"><span data-stu-id="333c2-223">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="333c2-224">Сведения об использовании более старой версии средств см. в разделе <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="333c2-224">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="333c2-225">Начиная с пакета SDK для .NET Core 2.1 (версия 2.1.300) поддерживается команда `dotnet ef`.</span><span class="sxs-lookup"><span data-stu-id="333c2-225">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="333c2-226">Это предупреждение означает, что проект предназначен для EF Core 1.0 или 1.1, которые несовместимы с пакетом SDK для .NET Core 2.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="333c2-226">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="333c2-227">Чтобы скомпилировать проект, установите пакет SDK для .NET Core 2.0 (версия 2.1.201) или более ранней версии на своем компьютере и определите необходимую версию пакета SDK с помощью файла *global.json*.</span><span class="sxs-lookup"><span data-stu-id="333c2-227">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="333c2-228">Дополнительные сведения о команде `dotnet ef` см. в разделе [Утилиты командной строки для EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="333c2-228">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="333c2-229">См. также</span><span class="sxs-lookup"><span data-stu-id="333c2-229">See also</span></span>

- [<span data-ttu-id="333c2-230">Как разрешаются пакеты SDK проекта</span><span class="sxs-lookup"><span data-stu-id="333c2-230">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
