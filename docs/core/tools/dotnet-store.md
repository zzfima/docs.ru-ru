---
title: "Команда dotnet store"
description: "Команда dotnet store сохраняет указанные сборки в хранилище пакетов среды выполнения."
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: fcf1eeba0709e05cff124bc3ae7bb93f4ca57128
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-store"></a><span data-ttu-id="73e0d-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="73e0d-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="73e0d-104">Имя</span><span class="sxs-lookup"><span data-stu-id="73e0d-104">Name</span></span>

<span data-ttu-id="73e0d-105">`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="73e0d-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="73e0d-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73e0d-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="73e0d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="73e0d-107">Description</span></span>

<span data-ttu-id="73e0d-108">`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="73e0d-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="73e0d-109">По умолчанию сборки оптимизируются для целевой среды выполнения и платформы.</span><span class="sxs-lookup"><span data-stu-id="73e0d-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="73e0d-110">Дополнительные сведения см. в разделе, посвященном [хранилищу пакетов среды выполнения](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="73e0d-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="73e0d-111">Обязательные параметры</span><span class="sxs-lookup"><span data-stu-id="73e0d-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="73e0d-112">Задает [целевую платформу](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="73e0d-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="73e0d-113">*Файл манифеста хранилища пакетов* — это XML-файл, содержащий список сохраняемых пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e0d-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="73e0d-114">Формат файла манифеста совместим с форматом *CSPROJ*.</span><span class="sxs-lookup"><span data-stu-id="73e0d-114">The format of the manifest file is compatible with the *csproj* format.</span></span> <span data-ttu-id="73e0d-115">Поэтому файл проекта *CSPROJ*, ссылающийся на требуемые пакеты, можно использовать с параметром `-m|--manifest` для сохранения сборок в хранилище пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="73e0d-115">So, a *csproj* project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="73e0d-116">Чтобы указать несколько файлов манифеста, добавьте параметр и путь для каждого из них: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="73e0d-116">To specify multiple manifest files, repeat the option and path for each file: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="73e0d-117">Идентификатор целевой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="73e0d-117">The runtime identifier to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="73e0d-118">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="73e0d-118">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="73e0d-119">Указывает версию пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="73e0d-119">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="73e0d-120">Этот параметр позволяет выбрать определенную версию платформы, отличную от версии, заданной с помощью параметра `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="73e0d-120">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="73e0d-121">Выводит справочные сведения.</span><span class="sxs-lookup"><span data-stu-id="73e0d-121">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="73e0d-122">Определяет путь к хранилищу пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="73e0d-122">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="73e0d-123">Если значение не указано, по умолчанию используется подкаталог *store* каталога установки .NET Core в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="73e0d-123">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="73e0d-124">Пропуск этапа оптимизации.</span><span class="sxs-lookup"><span data-stu-id="73e0d-124">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="73e0d-125">Пропуск создания символов.</span><span class="sxs-lookup"><span data-stu-id="73e0d-125">Skips symbol generation.</span></span> <span data-ttu-id="73e0d-126">В настоящее время символы можно создавать только в Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="73e0d-126">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="73e0d-127">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="73e0d-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="73e0d-128">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="73e0d-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="73e0d-129">Рабочий каталог, используемый командой.</span><span class="sxs-lookup"><span data-stu-id="73e0d-129">The working directory used by the command.</span></span> <span data-ttu-id="73e0d-130">Если значение не указано, используется подкаталог *obj* в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="73e0d-130">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="73e0d-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="73e0d-131">Examples</span></span>

<span data-ttu-id="73e0d-132">Сохранение пакетов, указанных в файле проекта *packages.csproj* для .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="73e0d-132">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="73e0d-133">Сохранение пакетов, указанных в файле *packages.csproj*, без оптимизации:</span><span class="sxs-lookup"><span data-stu-id="73e0d-133">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="73e0d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="73e0d-134">See also</span></span>

[<span data-ttu-id="73e0d-135">Хранилище пакетов среды выполнения</span><span class="sxs-lookup"><span data-stu-id="73e0d-135">Runtime package store</span></span>](../deploying/runtime-store.md)   

