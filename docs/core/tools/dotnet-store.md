---
title: Команда dotnet store
description: Команда dotnet store сохраняет указанные сборки в хранилище пакетов среды выполнения.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503581"
---
# <a name="dotnet-store"></a><span data-ttu-id="06cda-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="06cda-103">dotnet store</span></span>

<span data-ttu-id="06cda-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="06cda-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="06cda-105">Имя</span><span class="sxs-lookup"><span data-stu-id="06cda-105">Name</span></span>

<span data-ttu-id="06cda-106">`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="06cda-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="06cda-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06cda-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a><span data-ttu-id="06cda-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="06cda-108">Description</span></span>

<span data-ttu-id="06cda-109">`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="06cda-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="06cda-110">По умолчанию сборки оптимизируются для целевой среды выполнения и платформы.</span><span class="sxs-lookup"><span data-stu-id="06cda-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="06cda-111">Дополнительные сведения см. в разделе, посвященном [хранилищу пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="06cda-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="06cda-112">Обязательные параметры</span><span class="sxs-lookup"><span data-stu-id="06cda-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="06cda-113">Задает [целевую платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="06cda-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="06cda-114">Целевая платформа должна быть указана в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="06cda-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="06cda-115">*Файл манифеста хранилища пакетов* — это XML-файл, содержащий список сохраняемых пакетов.</span><span class="sxs-lookup"><span data-stu-id="06cda-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="06cda-116">Формат файла манифеста совместим с форматом проекта в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="06cda-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="06cda-117">Поэтому файл проекта, ссылающийся на требуемые пакеты, можно использовать с параметром `-m|--manifest` для сохранения сборок в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="06cda-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="06cda-118">Чтобы указать несколько файлов манифеста, добавьте параметр и путь для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="06cda-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="06cda-119">Пример: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="06cda-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="06cda-120">[Идентификатор целевой среды выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="06cda-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="06cda-121">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="06cda-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="06cda-122">Указывает версию пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="06cda-122">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="06cda-123">Этот параметр позволяет выбрать определенную версию платформы, отличную от версии, заданной с помощью параметра `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="06cda-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="06cda-124">Выводит справочные сведения.</span><span class="sxs-lookup"><span data-stu-id="06cda-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="06cda-125">Определяет путь к хранилищу пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="06cda-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="06cda-126">Если значение не указано, по умолчанию используется подкаталог *store* каталога установки .NET Core в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="06cda-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="06cda-127">Пропуск этапа оптимизации.</span><span class="sxs-lookup"><span data-stu-id="06cda-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="06cda-128">Пропуск создания символов.</span><span class="sxs-lookup"><span data-stu-id="06cda-128">Skips symbol generation.</span></span> <span data-ttu-id="06cda-129">В настоящее время символы можно создавать только в Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="06cda-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="06cda-130">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="06cda-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="06cda-131">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="06cda-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="06cda-132">Рабочий каталог, используемый командой.</span><span class="sxs-lookup"><span data-stu-id="06cda-132">The working directory used by the command.</span></span> <span data-ttu-id="06cda-133">Если значение не указано, используется подкаталог *obj* в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="06cda-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="06cda-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="06cda-134">Examples</span></span>

- <span data-ttu-id="06cda-135">Сохранение пакетов, указанных в файле проекта *packages.csproj* для .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="06cda-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="06cda-136">Сохранение пакетов, указанных в файле *packages.csproj*, без оптимизации:</span><span class="sxs-lookup"><span data-stu-id="06cda-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="06cda-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06cda-137">See also</span></span>

- [<span data-ttu-id="06cda-138">Хранилище пакетов среды выполнения</span><span class="sxs-lookup"><span data-stu-id="06cda-138">Runtime package store</span></span>](../deploying/runtime-store.md)
