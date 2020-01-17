---
title: Средство удаления
description: Обзор средства удаления .NET Core — интерактивного средства, позволяющего управлять очисткой пакетов SDK и сред выполнения .NET Core.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714543"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="cfd18-103">Средство удаления .NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd18-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="cfd18-104">[Средство удаления .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) позволяет удалять пакеты SDK и среды выполнения .NET Core из системы.</span><span class="sxs-lookup"><span data-stu-id="cfd18-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="cfd18-105">Указать версии, которые нужно удалить, можно с помощью ряда параметров.</span><span class="sxs-lookup"><span data-stu-id="cfd18-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="cfd18-106">Это средство поддерживают ОС Windows и macOS.</span><span class="sxs-lookup"><span data-stu-id="cfd18-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="cfd18-107">ОС Linux сейчас не поддерживает это средство.</span><span class="sxs-lookup"><span data-stu-id="cfd18-107">Linux is currently not supported.</span></span>

<span data-ttu-id="cfd18-108">В ОС Windows средство может удалять только пакеты SDK и среды выполнения, установленные с помощью одного из следующих установщиков:</span><span class="sxs-lookup"><span data-stu-id="cfd18-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="cfd18-109">установщик сред выполнения и пакетов SDK для .NET Core;</span><span class="sxs-lookup"><span data-stu-id="cfd18-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="cfd18-110">установщик Visual Studio более ранних версий, чем Visual Studio 2019 версии 16.3.</span><span class="sxs-lookup"><span data-stu-id="cfd18-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="cfd18-111">В macOS средство может удалять только пакеты SDK и среды выполнения, расположенные в папке */usr/local/share/dotnet*.</span><span class="sxs-lookup"><span data-stu-id="cfd18-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="cfd18-112">Из-за этих ограничений средство не сможет удалить все пакеты SDK и среды выполнения .NET Core на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfd18-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="cfd18-113">Вы можете использовать команду `dotnet --info`, чтобы найти все установленные пакеты SDK и среды выполнения .NET Core, в том числе те, которые не удается удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="cfd18-114">Команда `dotnet-core-uninstall list` позволяет просмотреть, какие пакеты SDK можно удалить с помощью средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="cfd18-115">Установка средства</span><span class="sxs-lookup"><span data-stu-id="cfd18-115">Install the tool</span></span>

<span data-ttu-id="cfd18-116">Средство удаления .NET Core можно скачать из репозитория GitHub [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="cfd18-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd18-117">Для удаления пакетов SDK и сред выполнения .NET Core средству требуются повышенные права.</span><span class="sxs-lookup"><span data-stu-id="cfd18-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="cfd18-118">Следовательно, его нужно устанавливать в защищенном от записи каталоге, например *C:\Program Files* в ОС Windows или */usr/local/bin* в macOS.</span><span class="sxs-lookup"><span data-stu-id="cfd18-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="cfd18-119">Ознакомьтесь также со статьей [Повышенные права доступа для команд dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="cfd18-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="cfd18-120">Подробные инструкции по установке доступны на [странице выпусков GitHub](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="cfd18-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="cfd18-121">Запуск программы</span><span class="sxs-lookup"><span data-stu-id="cfd18-121">Run the tool</span></span>

<span data-ttu-id="cfd18-122">Шаги ниже демонстрируют рекомендуемый подход к работе со средством удаления.</span><span class="sxs-lookup"><span data-stu-id="cfd18-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="cfd18-123">Шаг 1. Отображение установленных пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd18-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="cfd18-124">Шаг 2. Пробный запуск</span><span class="sxs-lookup"><span data-stu-id="cfd18-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="cfd18-125">Шаг 3. Удаление пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd18-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="cfd18-126">Шаг 4. Удаление резервной папки NuGet (необязательный)</span><span class="sxs-lookup"><span data-stu-id="cfd18-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="cfd18-127">Шаг 1. Отображение установленных пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd18-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="cfd18-128">Команда `dotnet-core-uninstall list` перечисляет установленные пакеты SDK и среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="cfd18-129">Некоторые пакеты SDK и среды выполнения могут требоваться для работы Visual Studio, и они отображаются с предупреждением о том, почему их не рекомендуется удалять.</span><span class="sxs-lookup"><span data-stu-id="cfd18-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="cfd18-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="cfd18-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cfd18-131">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cfd18-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="cfd18-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="cfd18-132">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="cfd18-133">Windows</span><span class="sxs-lookup"><span data-stu-id="cfd18-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="cfd18-134">Перечисляет все среды выполнения ASP.NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cfd18-135">Перечисляет все среды выполнения и пакеты размещения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="cfd18-136">Перечисляет все среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-137">Перечисляет все пакеты SDK для .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-138">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-138">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-139">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-140">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cfd18-141">Перечисляет все пакеты SDK и среды выполнения .NET Core x64, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="cfd18-142">Перечисляет все пакеты SDK и среды выполнения .NET Core x86, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="cfd18-143">macOS</span><span class="sxs-lookup"><span data-stu-id="cfd18-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="cfd18-144">Перечисляет все среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-145">Перечисляет все пакеты SDK для .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="cfd18-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-146">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-146">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-147">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-148">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="cfd18-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="cfd18-149">Examples</span></span>

* <span data-ttu-id="cfd18-150">Перечисление всех пакетов SDK и сред выполнения .NET Core, которые можно удалить с помощью этого средства:</span><span class="sxs-lookup"><span data-stu-id="cfd18-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="cfd18-151">Перечисление всех пакетов SDK и сред выполнения .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="cfd18-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="cfd18-152">Перечисление всех пакетов SDK для .NET Core x86:</span><span class="sxs-lookup"><span data-stu-id="cfd18-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="cfd18-153">Шаг 2. Пробный запуск</span><span class="sxs-lookup"><span data-stu-id="cfd18-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="cfd18-154">Команды `dotnet-core-uninstall dry-run` и `dotnet-core-uninstall whatif` позволяют просмотреть пакеты SDK и среды выполнения .NET Core, которые будут удалены, на основе указанных параметров без выполнения удаления.</span><span class="sxs-lookup"><span data-stu-id="cfd18-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="cfd18-155">Эти синонимичные команды.</span><span class="sxs-lookup"><span data-stu-id="cfd18-155">These commands are synonyms.</span></span>

<span data-ttu-id="cfd18-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="cfd18-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cfd18-157">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cfd18-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="cfd18-158">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cfd18-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="cfd18-159">Указанная версия для удаления.</span><span class="sxs-lookup"><span data-stu-id="cfd18-159">The specified version to uninstall.</span></span> <span data-ttu-id="cfd18-160">Вы можете перечислить несколько версий одну за другой, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="cfd18-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="cfd18-161">Поддерживаются также файлы ответов.</span><span class="sxs-lookup"><span data-stu-id="cfd18-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="cfd18-162">Файлы ответов можно использовать вместо того, чтобы указывать все версии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="cfd18-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="cfd18-163">Это текстовые файлы, обычно с расширением \*.rsp. Каждая версия указывается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="cfd18-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="cfd18-164">Чтобы указать файл ответов для аргумента `VERSION`, используйте символ \@ сразу после имени файла ответа.</span><span class="sxs-lookup"><span data-stu-id="cfd18-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="cfd18-165">Параметры</span><span class="sxs-lookup"><span data-stu-id="cfd18-165">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="cfd18-166">Windows</span><span class="sxs-lookup"><span data-stu-id="cfd18-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="cfd18-167">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cfd18-168">Удаляет только пакеты SDK и среды .NET Core, версия которых вышла раньше, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="cfd18-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="cfd18-169">Указанная версия не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cfd18-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cfd18-170">Удаляет все пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cfd18-171">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cfd18-172">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="cfd18-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cfd18-173">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="cfd18-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cfd18-174">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cfd18-175">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="cfd18-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="cfd18-176">Удаляет только среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cfd18-177">Удаляет только среду выполнения и пакеты размещения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cfd18-178">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cfd18-179">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-180">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-181">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-181">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-182">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-183">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cfd18-184">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x64.</span><span class="sxs-lookup"><span data-stu-id="cfd18-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="cfd18-185">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x86.</span><span class="sxs-lookup"><span data-stu-id="cfd18-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="cfd18-186">**`--force`** Принудительно удаляет версии, которые могут использоваться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cfd18-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="cfd18-187">Примечания.</span><span class="sxs-lookup"><span data-stu-id="cfd18-187">Notes:</span></span>

1. <span data-ttu-id="cfd18-188">Требуется только один из параметров `--sdk`, `--runtime`, `--aspnet-runtime` или `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="cfd18-189">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="cfd18-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="cfd18-190">Если `--x64` или `--x86` не указаны, будут удалены обе версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="cfd18-191">macOS</span><span class="sxs-lookup"><span data-stu-id="cfd18-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="cfd18-192">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cfd18-193">Удаляет пакеты SDK и среды выполнения .NET Core, версия которых вышла ранее, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="cfd18-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="cfd18-194">Указанная версия не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="cfd18-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cfd18-195">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cfd18-196">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cfd18-197">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="cfd18-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cfd18-198">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="cfd18-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cfd18-199">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cfd18-200">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="cfd18-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cfd18-201">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cfd18-202">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-203">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-204">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-204">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-205">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-206">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="cfd18-207">**`--force`** Принудительно удаляет версии, которые могут использоваться Visual Studio или пакетами SDK.</span><span class="sxs-lookup"><span data-stu-id="cfd18-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="cfd18-208">Примечания.</span><span class="sxs-lookup"><span data-stu-id="cfd18-208">Notes:</span></span>

1. <span data-ttu-id="cfd18-209">Требуется указать только один параметр: `--sdk` или `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="cfd18-210">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="cfd18-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="cfd18-211">Примеры</span><span class="sxs-lookup"><span data-stu-id="cfd18-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="cfd18-212">По умолчанию пакеты SDK и среды выполнения .NET Core, которые могут требоваться для работы Visual Studio или других пакетов SDK, не включаются в выходные данные `dotnet-core-uninstall dry-run`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="cfd18-213">В примерах ниже некоторые указанные пакеты SDK и среды выполнения могут быть исключены из выходных данных в зависимости от состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="cfd18-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="cfd18-214">Чтобы включить все пакеты SDK и среды выполнения, укажите их явно в качестве аргументов или используйте параметр `--force`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="cfd18-215">Пробный запуск удаления всех сред выполнения .NET Core, замененных более поздними версиями:</span><span class="sxs-lookup"><span data-stu-id="cfd18-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="cfd18-216">Пробный запуск удаления всех пакетов SDK для .NET Core, версия которых вышла раньше `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="cfd18-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="cfd18-217">Шаг 3. Удаление пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd18-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="cfd18-218">Команда `dotnet-core-uninstall remove` удаляет пакеты SDK и среды выполнения .NET Core, указанные с использованием коллекции параметров.</span><span class="sxs-lookup"><span data-stu-id="cfd18-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="cfd18-219">Средство нельзя использовать для удаления пакетов SDK и сред выполнения с версией 5.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="cfd18-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="cfd18-220">У средства разрушающее поведение, поэтому **настоятельно** рекомендуется выполнять пробный запуск перед выполнением команды удаления.</span><span class="sxs-lookup"><span data-stu-id="cfd18-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="cfd18-221">В ходе пробного запуска будут показаны пакеты SDK и среды .NET Core, подлежащие удалению при использовании команды `remove`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="cfd18-222">Чтобы узнать, какие пакеты SDK и среды выполнения безопасно удалять, обратитесь к разделу [Нужно ли удалять версию](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version).</span><span class="sxs-lookup"><span data-stu-id="cfd18-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="cfd18-223">Учитывайте следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="cfd18-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="cfd18-224">Это средство может удалять версии пакета SDK для .NET Core, необходимые для файлов `global.json` на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfd18-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="cfd18-225">Эти пакеты можно повторно установить, предварительно скачав их на [этой странице](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="cfd18-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="cfd18-226">Средство может удалять версии среды выполнения .NET Core, необходимые для зависимых от платформы приложений на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfd18-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="cfd18-227">Вы можете переустановить среду выполнения .NET Core, предварительно скачав ее с [этой страницы](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="cfd18-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="cfd18-228">Это средство может удалять версии пакета SDK и среды выполнения .NET Core, от которых зависит работа Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cfd18-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="cfd18-229">Если нарушите работу установленной версии Visual Studio, выполните команду "Исправить" в установщике Visual Studio, чтобы восстановить рабочее состояние.</span><span class="sxs-lookup"><span data-stu-id="cfd18-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="cfd18-230">По умолчанию все команды поддерживают пакеты SDK и среды выполнения .NET Core, которые могут потребоваться для работы Visual Studio или других пакетов SDK.</span><span class="sxs-lookup"><span data-stu-id="cfd18-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="cfd18-231">Эти пакеты и среды выполнения можно удалить путем их явного перечисления в виде аргументов или с использованием параметра `--force`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="cfd18-232">Для удаления пакетов SDK и сред выполнения .NET Core средству требуются повышенные права.</span><span class="sxs-lookup"><span data-stu-id="cfd18-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="cfd18-233">Запустите средство в командной строке администратора в ОС Windows или с помощью команды `sudo` в macOS.</span><span class="sxs-lookup"><span data-stu-id="cfd18-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="cfd18-234">Для команд `dry-run` и `whatif` повышение прав не требуется.</span><span class="sxs-lookup"><span data-stu-id="cfd18-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="cfd18-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="cfd18-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cfd18-236">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cfd18-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="cfd18-237">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cfd18-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="cfd18-238">Указанная версия для удаления.</span><span class="sxs-lookup"><span data-stu-id="cfd18-238">The specified version to uninstall.</span></span> <span data-ttu-id="cfd18-239">Вы можете перечислить несколько версий одну за другой, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="cfd18-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="cfd18-240">Поддерживаются также файлы ответов.</span><span class="sxs-lookup"><span data-stu-id="cfd18-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="cfd18-241">Файлы ответов можно использовать вместо того, чтобы указывать все версии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="cfd18-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="cfd18-242">Это текстовые файлы, обычно с расширением \*.rsp. Каждая версия указывается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="cfd18-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="cfd18-243">Чтобы указать файл ответов для аргумента `VERSION`, используйте символ \@ сразу после имени файла ответа.</span><span class="sxs-lookup"><span data-stu-id="cfd18-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="cfd18-244">Параметры</span><span class="sxs-lookup"><span data-stu-id="cfd18-244">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="cfd18-245">Windows</span><span class="sxs-lookup"><span data-stu-id="cfd18-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="cfd18-246">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cfd18-247">Удаляет только пакеты SDK и среды .NET Core, версия которых вышла раньше, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="cfd18-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="cfd18-248">Указанная версия не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cfd18-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cfd18-249">Удаляет все пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cfd18-250">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cfd18-251">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="cfd18-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cfd18-252">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="cfd18-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cfd18-253">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cfd18-254">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="cfd18-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="cfd18-255">Удаляет только среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="cfd18-256">Удаляет только среду выполнения и пакеты размещения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cfd18-257">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cfd18-258">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-259">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-260">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-260">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-261">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-262">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="cfd18-263">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x64.</span><span class="sxs-lookup"><span data-stu-id="cfd18-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="cfd18-264">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x86.</span><span class="sxs-lookup"><span data-stu-id="cfd18-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="cfd18-265">**`-y, --yes`** Выполняет команду без подтверждения Yes или No.</span><span class="sxs-lookup"><span data-stu-id="cfd18-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="cfd18-266">**`--force`** Принудительно удаляет версии, которые могут использоваться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cfd18-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="cfd18-267">Примечания.</span><span class="sxs-lookup"><span data-stu-id="cfd18-267">Notes:</span></span>

1. <span data-ttu-id="cfd18-268">Требуется только один из параметров `--sdk`, `--runtime`, `--aspnet-runtime` или `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="cfd18-269">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="cfd18-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="cfd18-270">Если `--x64` или `--x86` не указаны, будут удалены обе версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="cfd18-271">macOS</span><span class="sxs-lookup"><span data-stu-id="cfd18-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="cfd18-272">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="cfd18-273">Удаляет пакеты SDK и среды выполнения .NET Core, версия которых вышла ранее, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="cfd18-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="cfd18-274">Указанная версия не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="cfd18-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="cfd18-275">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="cfd18-276">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cfd18-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="cfd18-277">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="cfd18-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="cfd18-278">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="cfd18-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="cfd18-279">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="cfd18-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="cfd18-280">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="cfd18-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="cfd18-281">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="cfd18-282">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="cfd18-283">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cfd18-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="cfd18-284">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="cfd18-284">Sets the verbosity level.</span></span> <span data-ttu-id="cfd18-285">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cfd18-286">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-286">The default value is `normal`.</span></span>

* <span data-ttu-id="cfd18-287">**`-y, --yes`** Выполняет команду без подтверждения Yes или No.</span><span class="sxs-lookup"><span data-stu-id="cfd18-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="cfd18-288">**`--force`** Принудительно удаляет версии, которые могут использоваться Visual Studio или пакетами SDK.</span><span class="sxs-lookup"><span data-stu-id="cfd18-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="cfd18-289">Примечания.</span><span class="sxs-lookup"><span data-stu-id="cfd18-289">Notes:</span></span>

1. <span data-ttu-id="cfd18-290">Требуется указать только один параметр: `--sdk` или `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="cfd18-291">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="cfd18-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="cfd18-292">Примеры</span><span class="sxs-lookup"><span data-stu-id="cfd18-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="cfd18-293">По умолчанию пакеты SDK и среды выполнения .NET Core, которые могут требоваться для работы Visual Studio или других пакетов SDK, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cfd18-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="cfd18-294">В примерах ниже могут остаться некоторые из указанных пакетов SDK и сред выполнения в зависимости от состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="cfd18-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="cfd18-295">Чтобы удалить все пакеты и среды выполнения, укажите их явно в качестве аргументов или используйте параметр `--force`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="cfd18-296">Удаление всех сред выполнения .NET Core, кроме версии `3.0.0-preview6-27804-01` без подтверждения Yes или No:</span><span class="sxs-lookup"><span data-stu-id="cfd18-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="cfd18-297">Удаление всех пакетов SDK для .NET Core 1.1 без подтверждения Yes или No:</span><span class="sxs-lookup"><span data-stu-id="cfd18-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="cfd18-298">Удаление пакета SDK для .NET Core 1.1.11 без вывода на консоль:</span><span class="sxs-lookup"><span data-stu-id="cfd18-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="cfd18-299">Удаление всех пакетов SDK для .NET Core, которые можно безопасно удалить с помощью этого средства:</span><span class="sxs-lookup"><span data-stu-id="cfd18-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="cfd18-300">Удаление всех пакетов SDK для .NET Core, которые можно безопасно удалить с помощью этого средства, в том числе тех, которые могут требоваться для работы Visual Studio (не рекомендуется):</span><span class="sxs-lookup"><span data-stu-id="cfd18-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="cfd18-301">Удаление всех пакетов SDK для .NET Core, указанных в файле ответов `versions.rsp`:</span><span class="sxs-lookup"><span data-stu-id="cfd18-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="cfd18-302">В файле *versions.rsp* содержится следующее:</span><span class="sxs-lookup"><span data-stu-id="cfd18-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="cfd18-303">Шаг 4. Удаление резервной папки NuGet (необязательный)</span><span class="sxs-lookup"><span data-stu-id="cfd18-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="cfd18-304">В некоторых случаях папка `NuGetFallbackFolder` может больше не требоваться, и ее понадобится удалить.</span><span class="sxs-lookup"><span data-stu-id="cfd18-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="cfd18-305">Дополнительные сведения об удалении папки NuGetFallbackFolder см. в [этом разделе](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="cfd18-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="cfd18-306">Удаление средства</span><span class="sxs-lookup"><span data-stu-id="cfd18-306">Uninstall the tool</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="cfd18-307">Windows</span><span class="sxs-lookup"><span data-stu-id="cfd18-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="cfd18-308">Откройте окно **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="cfd18-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="cfd18-309">Найдите `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="cfd18-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="cfd18-310">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cfd18-310">Select **Uninstall**.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="cfd18-311">macOS</span><span class="sxs-lookup"><span data-stu-id="cfd18-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="cfd18-312">Удалите скачанный файл *dotnet-core-uninstall.tar.gz* из каталога, в котором он установлен.</span><span class="sxs-lookup"><span data-stu-id="cfd18-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="cfd18-313">Если содержимое этого файла распаковано в другой каталог, необходимо также удалить это содержимое.</span><span class="sxs-lookup"><span data-stu-id="cfd18-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
