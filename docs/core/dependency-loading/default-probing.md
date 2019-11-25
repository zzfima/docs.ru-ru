---
title: Стандартное зондирование (.NET Core)
description: Общие сведения о логике зондирования для поиска зависимостей в System.Runtime.Loader.AssemblyLoadContext.Default (.NET Core).
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2019
ms.locfileid: "72303686"
---
# <a name="default-probing"></a><span data-ttu-id="5a12b-103">Стандартное зондирование</span><span class="sxs-lookup"><span data-stu-id="5a12b-103">Default probing</span></span>

<span data-ttu-id="5a12b-104">Экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> отвечает за поиск зависимостей сборки.</span><span class="sxs-lookup"><span data-stu-id="5a12b-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="5a12b-105">В этой статье описана логика зондирования этого экземпляра <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a12b-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="5a12b-106">Свойства зондирования, настроенные узлом</span><span class="sxs-lookup"><span data-stu-id="5a12b-106">Host configured probing properties</span></span>

<span data-ttu-id="5a12b-107">Когда запускается среда выполнения, узел среды выполнения предоставляет набор именованных свойств зондирования, которые позволяют настроить пути зондирования в <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a12b-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="5a12b-108">Все свойства зондирования являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="5a12b-108">Each probing property is optional.</span></span> <span data-ttu-id="5a12b-109">Если свойство есть, оно представляет собой строковое значение со списком абсолютных путей с разделителями.</span><span class="sxs-lookup"><span data-stu-id="5a12b-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="5a12b-110">В качестве разделителя используется символ ";" в ОС Windows или ":" на всех других платформах.</span><span class="sxs-lookup"><span data-stu-id="5a12b-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="5a12b-111">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="5a12b-111">Property Name</span></span>                 |<span data-ttu-id="5a12b-112">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5a12b-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="5a12b-113">Список путей к файлам сборок платформы и приложения.</span><span class="sxs-lookup"><span data-stu-id="5a12b-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="5a12b-114">Список путей к каталогам, в которых выполняется поиск вспомогательных сборок ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5a12b-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="5a12b-115">Список путей к каталогам, в которых выполняется поиск неуправляемых (собственных) сборок.</span><span class="sxs-lookup"><span data-stu-id="5a12b-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="5a12b-116">Список путей к каталогам, в которых выполняется поиск управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="5a12b-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="5a12b-117">Список путей к каталогам, в которых выполняется поиск собственных образов для управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="5a12b-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="5a12b-118">Как задаются свойства?</span><span class="sxs-lookup"><span data-stu-id="5a12b-118">How are the properties populated?</span></span>

<span data-ttu-id="5a12b-119">Для установки значений свойств есть два основных сценария. Выбор между ними зависит от наличия файла *\<myapp>.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="5a12b-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="5a12b-120">Если файл *\*.deps.json* есть, для свойств зондирования задаются данные из этого файла.</span><span class="sxs-lookup"><span data-stu-id="5a12b-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="5a12b-121">Если файла *\*.deps.json* нет, предполагается, что все зависимости размещаются в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="5a12b-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="5a12b-122">В этом случае для свойств зондирования задается содержимое этого каталога.</span><span class="sxs-lookup"><span data-stu-id="5a12b-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="5a12b-123">Кроме того, аналогичным образом обрабатываются файлы *\*.deps.json* для всех упоминаемых платформ.</span><span class="sxs-lookup"><span data-stu-id="5a12b-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="5a12b-124">И, наконец, могут добавляться дополнительные зависимости из переменной среды `ADDITIONAL_DEPS`.</span><span class="sxs-lookup"><span data-stu-id="5a12b-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="5a12b-125">Как узнать свойства зондирования из управляемого кода?</span><span class="sxs-lookup"><span data-stu-id="5a12b-125">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="5a12b-126">Каждое свойство можно получить, вызвав функцию <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> с именем свойства. Список имен содержится в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="5a12b-126">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="5a12b-127">Как выполнять отладку формирования свойств зондирования?</span><span class="sxs-lookup"><span data-stu-id="5a12b-127">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="5a12b-128">Среда выполнения .NET Core будет выводить полезные сообщения трассировки, если настроены определенные переменные среды:</span><span class="sxs-lookup"><span data-stu-id="5a12b-128">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="5a12b-129">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="5a12b-129">Environment Variable</span></span>        |<span data-ttu-id="5a12b-130">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5a12b-130">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="5a12b-131">Включение трассировки.</span><span class="sxs-lookup"><span data-stu-id="5a12b-131">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="5a12b-132">Трассировка по указанному пути вместо стандартного `stderr`.</span><span class="sxs-lookup"><span data-stu-id="5a12b-132">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="5a12b-133">Настройка уровня детализации в диапазоне от 1 (минимальный) до 4 (максимальный).</span><span class="sxs-lookup"><span data-stu-id="5a12b-133">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="5a12b-134">Стандартное зондирование для управляемой сборки</span><span class="sxs-lookup"><span data-stu-id="5a12b-134">Managed assembly default probing</span></span>

<span data-ttu-id="5a12b-135">При зондировании для поиска управляемой сборки <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> выполняет перебор в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="5a12b-135">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="5a12b-136">файлы, соответствующие <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> в `TRUSTED_PLATFORM_ASSEMBLIES` (без учета расширений);</span><span class="sxs-lookup"><span data-stu-id="5a12b-136">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="5a12b-137">собственные сборки в файлах образов, расположенных в `APP_NI_PATHS`, с известным расширением файла;</span><span class="sxs-lookup"><span data-stu-id="5a12b-137">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="5a12b-138">файлы сборок, расположенные в `APP_PATHS`, с известным расширением файла.</span><span class="sxs-lookup"><span data-stu-id="5a12b-138">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="5a12b-139">Зондирование для поиска вспомогательной сборки (ресурса)</span><span class="sxs-lookup"><span data-stu-id="5a12b-139">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="5a12b-140">Чтобы найти вспомогательную сборку для определенного языка и региональных параметров, создайте структуру путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="5a12b-140">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="5a12b-141">Для каждого пути в `PLATFORM_RESOURCE_ROOTS` и далее в `APP_PATHS` добавьте строку <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, затем символ разделения каталогов, строку <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> и расширение .dll.</span><span class="sxs-lookup"><span data-stu-id="5a12b-141">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="5a12b-142">Если есть любой файл с одним из таких имен, попробуйте загрузить и вернуть его.</span><span class="sxs-lookup"><span data-stu-id="5a12b-142">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="5a12b-143">Зондирование для поиска неуправляемых (собственных) библиотек</span><span class="sxs-lookup"><span data-stu-id="5a12b-143">Unmanaged (native) library probing</span></span>

<span data-ttu-id="5a12b-144">При зондировании для поиска неуправляемой библиотеки, подходящие варианты проверяются в `NATIVE_DLL_SEARCH_DIRECTORIES`.</span><span class="sxs-lookup"><span data-stu-id="5a12b-144">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
