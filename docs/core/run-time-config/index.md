---
title: Конфигурация во время выполнения
description: Узнайте, как настроить приложения .NET Core с помощью параметров конфигурации среды выполнения.
ms.date: 11/13/2019
ms.openlocfilehash: e3922f6df81198b5e122f16d5cfc4b6d15cbb4ae
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567392"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="feb5d-103">Параметры конфигурации среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="feb5d-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="feb5d-104">.NET Core поддерживает использование файлов конфигурации и переменных среды для настройки поведения приложений .NET Core во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="feb5d-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="feb5d-105">Конфигурация среды выполнения является удобным вариантом в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="feb5d-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="feb5d-106">Вы не владеете исходным кодом приложения или не можете управлять им, поэтому вы не можете задать соответствующие настройки программным способом.</span><span class="sxs-lookup"><span data-stu-id="feb5d-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="feb5d-107">Вы одновременно запускаете несколько экземпляров приложения в одной системе и хотите настроить оптимальную производительность для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="feb5d-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="feb5d-108">Работа над этой документацией продолжается.</span><span class="sxs-lookup"><span data-stu-id="feb5d-108">This documentation is a work in progress.</span></span> <span data-ttu-id="feb5d-109">Если вы заметили, что приведенные здесь сведения являются неполными или неточными, [создайте сообщение о проблеме](https://github.com/dotnet/docs/issues), чтобы оповестить нас об этом, или [отправьте запрос на вытягивание](https://github.com/dotnet/docs/pulls) для этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="feb5d-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="feb5d-110">Сведения о том, как отправлять запросы на вытягивание для репозитория dotnet/docs, см. в [руководстве участника](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="feb5d-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="feb5d-111">.NET Core предоставляет следующие механизмы для настройки приложений во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="feb5d-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="feb5d-112">[Файл runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="feb5d-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="feb5d-113">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="feb5d-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="feb5d-114">Статьи в этом разделе документации упорядочены по категориям, например, "отладка" и "сборка мусора".</span><span class="sxs-lookup"><span data-stu-id="feb5d-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="feb5d-115">Приведены доступные параметры конфигурации для файла *runtimeconfig.json* (только .NET Core), для файла *app.config* (только .NET Framework) и для переменных среды.</span><span class="sxs-lookup"><span data-stu-id="feb5d-115">Available configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="feb5d-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="feb5d-116">runtimeconfig.json</span></span>

<span data-ttu-id="feb5d-117">Укажите параметры конфигурации среды выполнения в разделе **configProperties** файла *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="feb5d-117">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* file.</span></span> <span data-ttu-id="feb5d-118">Этот раздел имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="feb5d-118">This section has the form:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

<span data-ttu-id="feb5d-119">Ниже приведен пример файла:</span><span class="sxs-lookup"><span data-stu-id="feb5d-119">Here is an example file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

<span data-ttu-id="feb5d-120">Файл *runtimeconfig.json* автоматически создается в каталоге сборки командой [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="feb5d-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="feb5d-121">Он также создается при выборе пункта меню **Сборка** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="feb5d-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="feb5d-122">После создания файла его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="feb5d-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="feb5d-123">Значения некоторых параметров конфигурации также можно задать программным способом, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="feb5d-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="feb5d-124">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="feb5d-124">Environment variables</span></span>

<span data-ttu-id="feb5d-125">Переменные среды можно использовать для предоставления некоторых сведений о конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="feb5d-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="feb5d-126">Элементы конфигурации, указанные в качестве переменных среды, обычно имеют префикс **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="feb5d-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="feb5d-127">Переменные среды можно определить с помощью панели управления Windows, в командной строке или программным способом, вызвав метод <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> в Windows и системах на основе Unix.</span><span class="sxs-lookup"><span data-stu-id="feb5d-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="feb5d-128">В следующих примерах показано, как задать переменную среды в командной строке:</span><span class="sxs-lookup"><span data-stu-id="feb5d-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
