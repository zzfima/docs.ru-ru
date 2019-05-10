---
title: Функции Azure — Бессерверных приложений
description: Функции Azure предоставляют бессерверные возможности на разных языках (C#, JavaScript, Java) и платформы для предоставления управляемых событиями мгновенными масштабирование кода.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754230"
---
# <a name="azure-functions"></a><span data-ttu-id="6f32a-103">Проверка</span><span class="sxs-lookup"><span data-stu-id="6f32a-103">Azure Functions</span></span>

<span data-ttu-id="6f32a-104">Функции Azure предоставляют возможности бессерверных вычислений.</span><span class="sxs-lookup"><span data-stu-id="6f32a-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="6f32a-105">Функция вызывается с *триггера* (например, доступ к конечной точки HTTP или таймера) и выполняет тот фрагмент кода или бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="6f32a-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="6f32a-106">Функции, также специализированные поддержки *привязки* , подключаться к ресурсам, например хранилища и очереди.</span><span class="sxs-lookup"><span data-stu-id="6f32a-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Логотип функций Azure](./media/azure-functions-logo.png)

<span data-ttu-id="6f32a-108">Существуют две версии платформа функций Azure.</span><span class="sxs-lookup"><span data-stu-id="6f32a-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="6f32a-109">Прежняя версия поддерживает полную версию .NET Framework, а также новой среды выполнения поддерживает кросс платформенных приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f32a-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="6f32a-110">Дополнительные языки, помимо C# такие как JavaScript, F#, и поддерживаются Java.</span><span class="sxs-lookup"><span data-stu-id="6f32a-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="6f32a-111">Функции, созданные на портале предоставляют расширенный синтаксис скриптов.</span><span class="sxs-lookup"><span data-stu-id="6f32a-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="6f32a-112">Функции, которые создаются как автономные проекты могут развертываться с полной поддержки платформы и возможности.</span><span class="sxs-lookup"><span data-stu-id="6f32a-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="6f32a-113">Дополнительные сведения см. в разделе [документации по функциям Azure](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="6f32a-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="6f32a-114">Функции v1 и v2</span><span class="sxs-lookup"><span data-stu-id="6f32a-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="6f32a-115">Существуют две версии среды выполнения функций Azure: 1.x и 2.x.</span><span class="sxs-lookup"><span data-stu-id="6f32a-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="6f32a-116">Версии 1.x является общедоступной (GA).</span><span class="sxs-lookup"><span data-stu-id="6f32a-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="6f32a-117">Он поддерживает разработку .NET на портале или машин Windows и использует .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f32a-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="6f32a-118">1.x поддерживает C#, JavaScript, и F#, с помощью экспериментальную поддержку для Python, PHP, TypeScript, пакетной службы, Bash и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f32a-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="6f32a-119">[Версии 2.x также остается общедоступной теперь](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="6f32a-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="6f32a-120">Она использует .NET Core и поддерживает кросс платформенной разработки в Windows, macOS и Linux машин.</span><span class="sxs-lookup"><span data-stu-id="6f32a-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="6f32a-121">2.x первоклассную поддержку для Java, но пока не поддерживает непосредственно экспериментальных языков.</span><span class="sxs-lookup"><span data-stu-id="6f32a-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="6f32a-122">Версии 2.x использует новую модель расширяемости привязки, позволяющие расширениям сторонние платформы, независимое управление версиями из привязок, и отметить упрощение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f32a-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="6f32a-123">**Имеется известная проблема в версии 1.x с [поддержка перенаправления привязки](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="6f32a-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="6f32a-124">Проблема характерна для разработки .NET.</span><span class="sxs-lookup"><span data-stu-id="6f32a-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="6f32a-125">Затронутых проектов с помощью зависимостей от библиотек, которые имеют другую версию из библиотек, включенных в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f32a-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="6f32a-126">Себя взяла команда функции степени выполнения конкретную проблему.</span><span class="sxs-lookup"><span data-stu-id="6f32a-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="6f32a-127">Команда будут отвечать переадресации привязок в версии 2.x, прежде чем оно перемещается в общедоступной версии.</span><span class="sxs-lookup"><span data-stu-id="6f32a-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="6f32a-128">Официальный блог группы инструкции с предлагаемые исправления и способы их устранения можно найти здесь: [Разрешения сборки в функциях Azure](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="6f32a-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="6f32a-129">Дополнительные сведения см. в разделе [сравнение 1.x и 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="6f32a-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="6f32a-130">Поддержка языков программирования</span><span class="sxs-lookup"><span data-stu-id="6f32a-130">Programming language support</span></span>

<span data-ttu-id="6f32a-131">Поддерживаются следующие языки либо вообще доступности (GA), просматривать, или экспериментальные.</span><span class="sxs-lookup"><span data-stu-id="6f32a-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="6f32a-132">Язык</span><span class="sxs-lookup"><span data-stu-id="6f32a-132">Language</span></span>      |<span data-ttu-id="6f32a-133">1.x</span><span class="sxs-lookup"><span data-stu-id="6f32a-133">1.x</span></span>         |<span data-ttu-id="6f32a-134">2.x</span><span class="sxs-lookup"><span data-stu-id="6f32a-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="6f32a-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="6f32a-135">**C#**</span></span>        |<span data-ttu-id="6f32a-136">ОБЩЕДОСТУПНАЯ ВЕРСИЯ</span><span class="sxs-lookup"><span data-stu-id="6f32a-136">GA</span></span>          |<span data-ttu-id="6f32a-137">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="6f32a-137">Preview</span></span>  |
|<span data-ttu-id="6f32a-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="6f32a-138">**JavaScript**</span></span>|<span data-ttu-id="6f32a-139">ОБЩЕДОСТУПНАЯ ВЕРСИЯ</span><span class="sxs-lookup"><span data-stu-id="6f32a-139">GA</span></span>          |<span data-ttu-id="6f32a-140">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="6f32a-140">Preview</span></span>  |
|<span data-ttu-id="6f32a-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="6f32a-141">**F#**</span></span>        |<span data-ttu-id="6f32a-142">ОБЩЕДОСТУПНАЯ ВЕРСИЯ</span><span class="sxs-lookup"><span data-stu-id="6f32a-142">GA</span></span>          |         |
|<span data-ttu-id="6f32a-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="6f32a-143">**Java**</span></span>      |            |<span data-ttu-id="6f32a-144">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="6f32a-144">Preview</span></span>  |
|<span data-ttu-id="6f32a-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="6f32a-145">**Python**</span></span>    |<span data-ttu-id="6f32a-146">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-146">Experimental</span></span>|         |
|<span data-ttu-id="6f32a-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="6f32a-147">**PHP**</span></span>       |<span data-ttu-id="6f32a-148">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-148">Experimental</span></span>|         |
|<span data-ttu-id="6f32a-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="6f32a-149">**TypeScript**</span></span>|<span data-ttu-id="6f32a-150">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-150">Experimental</span></span>|         |
|<span data-ttu-id="6f32a-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="6f32a-151">**Batch**</span></span>     |<span data-ttu-id="6f32a-152">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-152">Experimental</span></span>|         |
|<span data-ttu-id="6f32a-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="6f32a-153">**Bash**</span></span>      |<span data-ttu-id="6f32a-154">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-154">Experimental</span></span>|         |
|<span data-ttu-id="6f32a-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6f32a-155">**PowerShell**</span></span>|<span data-ttu-id="6f32a-156">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="6f32a-156">Experimental</span></span>|         |

<span data-ttu-id="6f32a-157">Дополнительные сведения см. в разделе [поддерживаемые языки](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="6f32a-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="6f32a-158">Планы службы приложений</span><span class="sxs-lookup"><span data-stu-id="6f32a-158">App service plans</span></span>

<span data-ttu-id="6f32a-159">Функции обеспечиваются *план службы приложений*.</span><span class="sxs-lookup"><span data-stu-id="6f32a-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="6f32a-160">План определяет ресурсы, используемые приложением функции.</span><span class="sxs-lookup"><span data-stu-id="6f32a-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="6f32a-161">Можно назначить планы в регионе, определить размер и количество виртуальных машин, которые будут использоваться и Выбор ценовой категории.</span><span class="sxs-lookup"><span data-stu-id="6f32a-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="6f32a-162">Значение true, бессерверной архитектурой, могут установить приложения-функции **потребления** плана.</span><span class="sxs-lookup"><span data-stu-id="6f32a-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="6f32a-163">План потребления масштабируется автоматически на основе нагрузки серверной части.</span><span class="sxs-lookup"><span data-stu-id="6f32a-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="6f32a-164">Дополнительные сведения см. в разделе [планов службы приложений](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="6f32a-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="6f32a-165">Создание первой функции</span><span class="sxs-lookup"><span data-stu-id="6f32a-165">Create your first function</span></span>

<span data-ttu-id="6f32a-166">Существуют три распространенных способов создания приложения-функции.</span><span class="sxs-lookup"><span data-stu-id="6f32a-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="6f32a-167">Функции скрипта на портале.</span><span class="sxs-lookup"><span data-stu-id="6f32a-167">Script functions in the portal.</span></span>
* <span data-ttu-id="6f32a-168">Создание необходимых ресурсов с помощью интерфейса командной строки Azure (CLI).</span><span class="sxs-lookup"><span data-stu-id="6f32a-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="6f32a-169">Создание функций локально с помощью вашей любимой интегрированной среде разработки и их публикации в Azure.</span><span class="sxs-lookup"><span data-stu-id="6f32a-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="6f32a-170">Дополнительные сведения о создании сценариев функции на портале, см. в разделе [Создание первой функции на портале Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="6f32a-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="6f32a-171">Чтобы выполнить сборку с помощью Azure CLI, см. в разделе [Создание первой функции с помощью Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="6f32a-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="6f32a-172">Создание функции из Visual Studio, см. в разделе [Создание первой функции с помощью Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6f32a-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="6f32a-173">Понять, триггеры и привязки</span><span class="sxs-lookup"><span data-stu-id="6f32a-173">Understand triggers and bindings</span></span>

<span data-ttu-id="6f32a-174">Функции вызываются *триггера* и может иметь только одно.</span><span class="sxs-lookup"><span data-stu-id="6f32a-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="6f32a-175">Помимо вызова функции, определенные триггеры также служат в качестве привязки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="6f32a-176">Можно также определить несколько привязок, а также триггер.</span><span class="sxs-lookup"><span data-stu-id="6f32a-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="6f32a-177">*Привязки* предоставляют декларативный способ подключения данных в код.</span><span class="sxs-lookup"><span data-stu-id="6f32a-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="6f32a-178">Они могут передаваться in (входные) или принимать данные (output).</span><span class="sxs-lookup"><span data-stu-id="6f32a-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="6f32a-179">Триггеры и привязки позволяют упростить функции для работы с.</span><span class="sxs-lookup"><span data-stu-id="6f32a-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="6f32a-180">Привязки удалите затраты на вручную создание базы данных или файла подключений системы.</span><span class="sxs-lookup"><span data-stu-id="6f32a-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="6f32a-181">Все сведения, необходимые для привязок, содержатся в специальной *файле Functions.JSON, используются* файлов для скриптов или объявлен с атрибутами в коде.</span><span class="sxs-lookup"><span data-stu-id="6f32a-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="6f32a-182">Некоторые распространенные триггеры включают:</span><span class="sxs-lookup"><span data-stu-id="6f32a-182">Some common triggers include:</span></span>

* <span data-ttu-id="6f32a-183">Хранилище BLOB-объектов: вызов функции, при отправке или изменены в хранилище файла или папки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="6f32a-184">HTTP: вызов функции например REST API.</span><span class="sxs-lookup"><span data-stu-id="6f32a-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="6f32a-185">Очередь: вызовите функции по завершении элементы существуют в очереди.</span><span class="sxs-lookup"><span data-stu-id="6f32a-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="6f32a-186">Таймер: вызов функции регулярно выпускать.</span><span class="sxs-lookup"><span data-stu-id="6f32a-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="6f32a-187">Примеры привязок.</span><span class="sxs-lookup"><span data-stu-id="6f32a-187">Examples of bindings include:</span></span>

* <span data-ttu-id="6f32a-188">Cosmos DB: легко подключаться к базе данных для загрузки и сохранения файлов.</span><span class="sxs-lookup"><span data-stu-id="6f32a-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="6f32a-189">Хранилище таблиц: работа с хранилищем ключей и значений из приложения-функции.</span><span class="sxs-lookup"><span data-stu-id="6f32a-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="6f32a-190">Хранилище очередей: легко извлекать элементы из очереди, или поместите новые элементы в очереди.</span><span class="sxs-lookup"><span data-stu-id="6f32a-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="6f32a-191">Следующий пример *файле Functions.JSON, используются* файл определяет триггер и привязки:</span><span class="sxs-lookup"><span data-stu-id="6f32a-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="6f32a-192">В этом примере, эта функция активируется при изменении хранилища BLOB-объектов в `images` контейнера.</span><span class="sxs-lookup"><span data-stu-id="6f32a-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="6f32a-193">Сведения для файла передается в, чтобы триггер также выступает в качестве привязки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="6f32a-194">Существует другая привязка для размещения сведений о в очередь с именем `images`.</span><span class="sxs-lookup"><span data-stu-id="6f32a-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="6f32a-195">Ниже приведен скрипт C# для функции.</span><span class="sxs-lookup"><span data-stu-id="6f32a-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="6f32a-196">Пример является простой функции, которая принимает имя файла, который был изменен или хранилище BLOB-объектов и помещает его в очередь для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="6f32a-197">Полный список триггеров и привязок см. в разделе [триггеры функций Azure и основные понятия привязки](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="6f32a-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="6f32a-198">Прокси-элементы</span><span class="sxs-lookup"><span data-stu-id="6f32a-198">Proxies</span></span>

<span data-ttu-id="6f32a-199">Прокси-серверы предоставляют функциональные возможности перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="6f32a-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="6f32a-200">Учетные записи-посредники предоставлять конечную точку и сопоставить эту конечную точку на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="6f32a-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="6f32a-201">С помощью прокси-серверы вы можете:</span><span class="sxs-lookup"><span data-stu-id="6f32a-201">With proxies, you can:</span></span>

* <span data-ttu-id="6f32a-202">Перенаправление входящего запроса на другую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="6f32a-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="6f32a-203">Измените входящего запроса, прежде чем передается вместе.</span><span class="sxs-lookup"><span data-stu-id="6f32a-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="6f32a-204">Измените или предоставления ответа.</span><span class="sxs-lookup"><span data-stu-id="6f32a-204">Modify or provide a response.</span></span>

<span data-ttu-id="6f32a-205">Прокси-серверы используются для сценариев, таких как:</span><span class="sxs-lookup"><span data-stu-id="6f32a-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="6f32a-206">Упростить, сократить или изменить URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="6f32a-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="6f32a-207">Предоставление согласованного префикса API к нескольким службам серверной части.</span><span class="sxs-lookup"><span data-stu-id="6f32a-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="6f32a-208">Макетирование ответа на конечной стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="6f32a-209">Предоставление статических ответ известной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f32a-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="6f32a-210">Поддержание соответствия конечную точку API во время перемещения или миграции серверной части.</span><span class="sxs-lookup"><span data-stu-id="6f32a-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="6f32a-211">Прокси-серверы хранятся в виде определения JSON.</span><span class="sxs-lookup"><span data-stu-id="6f32a-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="6f32a-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="6f32a-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="6f32a-213">`Domain Redirect` Прокси-сервер принимает сокращенный маршрут и сопоставляет его больше ресурсов функции.</span><span class="sxs-lookup"><span data-stu-id="6f32a-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="6f32a-214">Преобразование выглядит так:</span><span class="sxs-lookup"><span data-stu-id="6f32a-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="6f32a-215">`Root` Прокси-сервер принимает все отправляемые корневой URL-адрес (`https://--shorturl--/`) и перенаправляет его на сайте документации.</span><span class="sxs-lookup"><span data-stu-id="6f32a-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="6f32a-216">Пример использования учетных записей-посредников показан в видео [Azure: Перенос приложения в облако с помощью бессерверных функций Azure](https://channel9.msdn.com/events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="6f32a-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="6f32a-217">В режиме реального времени приложения ASP.NET Core, работающего на локальном сервере SQL Server переносятся в облако Azure.</span><span class="sxs-lookup"><span data-stu-id="6f32a-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="6f32a-218">Прокси-серверы используются для рефакторинг проект традиционных веб-API с помощью функций.</span><span class="sxs-lookup"><span data-stu-id="6f32a-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="6f32a-219">Дополнительные сведения о прокси-серверов, см. в разделе [работы с прокси функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="6f32a-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6f32a-220">[Назад](azure-serverless-platform.md)
>[Вперед](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="6f32a-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
