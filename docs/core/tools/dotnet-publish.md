---
title: Команда dotnet publish
description: Команда dotnet publish публикует решение или проект .NET Core в каталоге.
ms.date: 02/24/2020
ms.openlocfilehash: cf41ee09244faad03feb8ccda19135b8c7780106
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157003"
---
# <a name="dotnet-publish"></a><span data-ttu-id="5e46f-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="5e46f-103">dotnet publish</span></span>

<span data-ttu-id="5e46f-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5e46f-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5e46f-105">name</span><span class="sxs-lookup"><span data-stu-id="5e46f-105">Name</span></span>

<span data-ttu-id="5e46f-106">`dotnet publish` — публикует приложение и его зависимости в папке для развертывания на размещающей системе.</span><span class="sxs-lookup"><span data-stu-id="5e46f-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5e46f-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5e46f-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration] 
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5e46f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5e46f-108">Description</span></span>

<span data-ttu-id="5e46f-109">`dotnet publish` компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="5e46f-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="5e46f-110">Выходные данные включают следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="5e46f-110">The output includes the following assets:</span></span>

- <span data-ttu-id="5e46f-111">Код на промежуточном языке (IL) в сборке с расширением *DLL*.</span><span class="sxs-lookup"><span data-stu-id="5e46f-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="5e46f-112">Файл *.deps.json*, содержащий все зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="5e46f-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="5e46f-113">Файл *.runtimeconfig.json*, определяющий общую среду выполнения, которую ожидает приложение, а также другие параметры конфигурации для среды выполнения (например, тип сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="5e46f-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="5e46f-114">Зависимости приложения, которые копируются из кэша NuGet в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="5e46f-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="5e46f-115">Выходные данные команды `dotnet publish` готовы к развертыванию в размещающей системе (например, на сервере, ПК, Mac, ноутбуке) для выполнения.</span><span class="sxs-lookup"><span data-stu-id="5e46f-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="5e46f-116">Это единственный официальный способ подготовить приложение к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5e46f-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="5e46f-117">В зависимости от указанного в проекте типа развертывания размещающая система может как иметь, так и не иметь общую среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e46f-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="5e46f-118">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5e46f-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="5e46f-119">Проект или решение для публикации.</span><span class="sxs-lookup"><span data-stu-id="5e46f-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="5e46f-120">`PROJECT` — это путь или имя файла проекта [C#](csproj.md), F# или Visual Basic либо путь к папке, которая содержит файл проекта C#, F# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5e46f-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="5e46f-121">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="5e46f-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="5e46f-122">`SOLUTION` — это путь и имя для файла решения (расширение *SLN*) или путь к каталогу, содержащему файл решения.</span><span class="sxs-lookup"><span data-stu-id="5e46f-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="5e46f-123">Если каталог не указан, по умолчанию используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="5e46f-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="5e46f-124">**Доступно начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5e46f-124">**Available starting with .NET Core 3.0 SDK.**</span></span> 

## <a name="options"></a><span data-ttu-id="5e46f-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e46f-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="5e46f-126">Определяет конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="5e46f-126">Defines the build configuration.</span></span> <span data-ttu-id="5e46f-127">По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="5e46f-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5e46f-128">Публикует приложение для указанной [целевой платформы](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5e46f-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="5e46f-129">Вам нужно указать целевую платформу в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5e46f-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="5e46f-130">Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="5e46f-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="5e46f-131">Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="5e46f-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5e46f-132">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="5e46f-132">Prints out a short help for the command.</span></span>

- <span data-ttu-id="5e46f-133">**`--interactive`** **Доступно начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5e46f-133">**`--interactive`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="5e46f-134">Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные.</span><span class="sxs-lookup"><span data-stu-id="5e46f-134">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="5e46f-135">Например, чтобы завершить проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5e46f-135">For example, to complete authentication.</span></span> 

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="5e46f-136">Определяет один или несколько [целевых манифестов](../deploying/runtime-store.md) для усечения множества пакетов, публикуемых вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="5e46f-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="5e46f-137">Файл манифеста является частью выходных данных [команды `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="5e46f-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="5e46f-138">Чтобы указать несколько манифестов, добавьте параметр `--manifest` для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="5e46f-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="5e46f-139">Не выполняет сборку проекта перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="5e46f-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="5e46f-140">Он также неявно задает флаг `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="5e46f-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="5e46f-141">Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.</span><span class="sxs-lookup"><span data-stu-id="5e46f-141">Ignores project-to-project references and only restores the root project.</span></span>

- <span data-ttu-id="5e46f-142">**`--nologo`** **Доступно начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5e46f-142">**`--nologo`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="5e46f-143">Скрывает загрузочный баннер или сообщение об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="5e46f-143">Doesn't display the startup banner or the copyright message.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="5e46f-144">Не выполняет неявное восстановление при выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="5e46f-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5e46f-145">Задает путь для выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="5e46f-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="5e46f-146">Если значение не указано, для исполняемого файла, зависящего от среды выполнения, а также для кроссплатформенных двоичных файлов по умолчанию используется *./bin/[configuration]/[framework]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="5e46f-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="5e46f-147">Для автономного исполняемого файла по умолчанию используется *./bin/[configuration]/[framework]/[runtime]/publish/* .</span><span class="sxs-lookup"><span data-stu-id="5e46f-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="5e46f-148">Если указан относительный путь, созданный выходной каталог задается относительно расположения файла проекта, а не текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="5e46f-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="5e46f-149">Публикует среду выполнения .NET Core вместе с приложением, что позволяет не устанавливать ее на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5e46f-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="5e46f-150">Если указан идентификатор среды выполнения, значение по умолчанию равно `true`.</span><span class="sxs-lookup"><span data-stu-id="5e46f-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="5e46f-151">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="5e46f-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- <span data-ttu-id="5e46f-152">**`--no-self-contained`**  **Доступно начиная с пакета SDK для .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="5e46f-152">**`--no-self-contained`**  **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="5e46f-153">Эквивалент `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="5e46f-153">Equivalent to `--self-contained false`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="5e46f-154">Публикует приложение для данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5e46f-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="5e46f-155">Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5e46f-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="5e46f-156">Дополнительные сведения см. в разделах [Публикация приложения .NET Core](../deploying/index.md) и [Публикация приложений .NET Core с помощью .NET Core CLI](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="5e46f-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5e46f-157">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="5e46f-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5e46f-158">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5e46f-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="5e46f-159">Определяет суффикс версии для замены звездочки (`*`) в поле версия файла проекта.</span><span class="sxs-lookup"><span data-stu-id="5e46f-159">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="5e46f-160">Примеры</span><span class="sxs-lookup"><span data-stu-id="5e46f-160">Examples</span></span>

- <span data-ttu-id="5e46f-161">Создание [кроссплатформенного двоичного файла, зависящего от среды выполнения,](../deploying/index.md#produce-a-cross-platform-binary) для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="5e46f-161">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="5e46f-162">Начиная с пакета SDK для .NET Core 3.0 этот пример также создает [зависящий от среды выполнения исполняемый файл](../deploying/index.md#publish-runtime-dependent) для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="5e46f-162">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="5e46f-163">Создание [автономного исполняемого файла](../deploying/index.md#publish-self-contained) для проекта в текущем каталоге для конкретной среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="5e46f-163">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="5e46f-164">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5e46f-164">The RID must be in the project file.</span></span>

- <span data-ttu-id="5e46f-165">Создание [зависящего от среды выполнения исполняемого файла](../deploying/index.md#publish-runtime-dependent) для проекта в текущем каталоге для конкретной платформы:</span><span class="sxs-lookup"><span data-stu-id="5e46f-165">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="5e46f-166">Идентификатор RID должен находиться в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="5e46f-166">The RID must be in the project file.</span></span> <span data-ttu-id="5e46f-167">Этот пример относится к пакету SDK для .NET Core 3.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="5e46f-167">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="5e46f-168">Публикация проекта в текущем каталоге для конкретной среды выполнения и целевой платформы:</span><span class="sxs-lookup"><span data-stu-id="5e46f-168">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="5e46f-169">Публикация указанного файла проекта:</span><span class="sxs-lookup"><span data-stu-id="5e46f-169">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="5e46f-170">Публикация текущего приложения с обработкой только корневого проекта, без восстановления ссылок между проектами (P2P), во время операции восстановления:</span><span class="sxs-lookup"><span data-stu-id="5e46f-170">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="5e46f-171">См. также</span><span class="sxs-lookup"><span data-stu-id="5e46f-171">See also</span></span>

- [<span data-ttu-id="5e46f-172">Общие сведения о публикации приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e46f-172">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="5e46f-173">Публикация приложений .NET Core с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="5e46f-173">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="5e46f-174">Целевые платформы</span><span class="sxs-lookup"><span data-stu-id="5e46f-174">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="5e46f-175">Каталог идентификаторов сред выполнения (RID)</span><span class="sxs-lookup"><span data-stu-id="5e46f-175">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- <span data-ttu-id="5e46f-176">[Работа с заверением macOS Catalina](../install/macos-notarization-issues.md) Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="5e46f-176">[Working with macOS Catalina Notarization](../install/macos-notarization-issues.md) For more information, see he following resources:</span></span>
- [<span data-ttu-id="5e46f-177">Структура каталогов опубликованного приложения</span><span class="sxs-lookup"><span data-stu-id="5e46f-177">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
