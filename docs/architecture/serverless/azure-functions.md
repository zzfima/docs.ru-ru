---
title: Функции Azure — бессерверные приложения
description: Функции Azure предоставляют бессерверные возможности на нескольких языках (C#, JavaScript, Java) и платформах для обеспечения управляемого событиями кода мгновенного масштабирования.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5e8187b3752a0f0d0bcf8e15f2ce440dc5a64e45
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522876"
---
# <a name="azure-functions"></a><span data-ttu-id="b52b8-103">Проверка</span><span class="sxs-lookup"><span data-stu-id="b52b8-103">Azure Functions</span></span>

<span data-ttu-id="b52b8-104">Функции Azure предоставляют бессерверные возможности вычислений.</span><span class="sxs-lookup"><span data-stu-id="b52b8-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="b52b8-105">Функция вызывается *триггером* (например, доступ к конечной точке HTTP или срабатывание по таймеру) и выполняет блок кода или бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="b52b8-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="b52b8-106">Функции также поддерживают специализированные *привязки*, которые подключаются к таким ресурсам, как хранилище и очереди.</span><span class="sxs-lookup"><span data-stu-id="b52b8-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Логотип Функций Azure](./media/azure-functions-logo.png)

<span data-ttu-id="b52b8-108">Существует две версии платформы "Функции Azure".</span><span class="sxs-lookup"><span data-stu-id="b52b8-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="b52b8-109">Традиционная версия поддерживает полную.NET Framework, а новая среда выполнения — кроссплатформенные приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b52b8-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="b52b8-110">Помимо C# поддерживаются дополнительные языки, такие как JavaScript, F# и Java.</span><span class="sxs-lookup"><span data-stu-id="b52b8-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="b52b8-111">Функции, созданные на портале, предоставляют расширенный синтаксис написания скриптов.</span><span class="sxs-lookup"><span data-stu-id="b52b8-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="b52b8-112">Функции, созданные как отдельные проекты, могут быть развернуты с полной поддержкой и возможностями платформы.</span><span class="sxs-lookup"><span data-stu-id="b52b8-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="b52b8-113">Дополнительные сведения см. в [документации по Функциям Azure](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="b52b8-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="b52b8-114">Функции версии 1 и 2</span><span class="sxs-lookup"><span data-stu-id="b52b8-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="b52b8-115">Существует две версии среды выполнения Функций Azure: 1.x и 2.x.</span><span class="sxs-lookup"><span data-stu-id="b52b8-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="b52b8-116">Версия 1.x является общедоступной.</span><span class="sxs-lookup"><span data-stu-id="b52b8-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="b52b8-117">Она поддерживает разработку на .NET на портале или на компьютерах с Windows и использует .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b52b8-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="b52b8-118">Версия 1.x поддерживает C#, JavaScript и F#, а также в экспериментальном режиме Python, PHP, TypeScript, Batch, Bash и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b52b8-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="b52b8-119">[Версия 2.x также теперь общедоступна](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="b52b8-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="b52b8-120">Она использует .NET Core и поддерживает кроссплатформенную разработку на компьютерах с Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="b52b8-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="b52b8-121">В версии 2.x добавлена первоклассная поддержка Java, но она пока еще не поддерживает ни один из экспериментальных языков.</span><span class="sxs-lookup"><span data-stu-id="b52b8-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="b52b8-122">Версия 2.x использует новую модель расширяемости привязки, которая обеспечивает поддержку сторонних расширений для платформы, независимые версии привязок и более рациональную среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b52b8-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="b52b8-123">**В версии 1.x существует известная ошибка с [поддержкой перенаправления привязки](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="b52b8-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="b52b8-124">Эта ошибка характерна для разработки на .NET.</span><span class="sxs-lookup"><span data-stu-id="b52b8-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="b52b8-125">Она влияет на проекты с зависимостями от библиотек, версия которых отличается от библиотек, включенных в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b52b8-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="b52b8-126">Команда по разработке функций взяла на себя обязательство добиться конкретного прогресса в решении проблемы.</span><span class="sxs-lookup"><span data-stu-id="b52b8-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="b52b8-127">Команда рассмотрит перенаправления привязки в версии 2.x, прежде чем она станет общедоступной.</span><span class="sxs-lookup"><span data-stu-id="b52b8-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="b52b8-128">Официальное заявление команды с предлагаемыми исправлениями и решениями можно найти здесь: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions) (Разрешение сборок в Функциях Azure).</span><span class="sxs-lookup"><span data-stu-id="b52b8-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="b52b8-129">Дополнительные сведения см. в статье [Azure Functions runtime versions overview](https://docs.microsoft.com/azure/azure-functions/functions-versions) (Обзор версий среды выполнения для решения "Функции Azure").</span><span class="sxs-lookup"><span data-stu-id="b52b8-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="b52b8-130">Поддержка языков программирования</span><span class="sxs-lookup"><span data-stu-id="b52b8-130">Programming language support</span></span>

<span data-ttu-id="b52b8-131">В общедоступной, предварительной и экспериментальной версиях поддерживаются следующие языки.</span><span class="sxs-lookup"><span data-stu-id="b52b8-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="b52b8-132">Язык</span><span class="sxs-lookup"><span data-stu-id="b52b8-132">Language</span></span>      |<span data-ttu-id="b52b8-133">1.x</span><span class="sxs-lookup"><span data-stu-id="b52b8-133">1.x</span></span>         |<span data-ttu-id="b52b8-134">2.x</span><span class="sxs-lookup"><span data-stu-id="b52b8-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="b52b8-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="b52b8-135">**C#**</span></span>        |<span data-ttu-id="b52b8-136">GA</span><span class="sxs-lookup"><span data-stu-id="b52b8-136">GA</span></span>          |<span data-ttu-id="b52b8-137">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="b52b8-137">Preview</span></span>  |
|<span data-ttu-id="b52b8-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="b52b8-138">**JavaScript**</span></span>|<span data-ttu-id="b52b8-139">GA</span><span class="sxs-lookup"><span data-stu-id="b52b8-139">GA</span></span>          |<span data-ttu-id="b52b8-140">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="b52b8-140">Preview</span></span>  |
|<span data-ttu-id="b52b8-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="b52b8-141">**F#**</span></span>        |<span data-ttu-id="b52b8-142">GA</span><span class="sxs-lookup"><span data-stu-id="b52b8-142">GA</span></span>          |         |
|<span data-ttu-id="b52b8-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="b52b8-143">**Java**</span></span>      |            |<span data-ttu-id="b52b8-144">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="b52b8-144">Preview</span></span>  |
|<span data-ttu-id="b52b8-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="b52b8-145">**Python**</span></span>    |<span data-ttu-id="b52b8-146">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-146">Experimental</span></span>|         |
|<span data-ttu-id="b52b8-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="b52b8-147">**PHP**</span></span>       |<span data-ttu-id="b52b8-148">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-148">Experimental</span></span>|         |
|<span data-ttu-id="b52b8-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="b52b8-149">**TypeScript**</span></span>|<span data-ttu-id="b52b8-150">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-150">Experimental</span></span>|         |
|<span data-ttu-id="b52b8-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="b52b8-151">**Batch**</span></span>     |<span data-ttu-id="b52b8-152">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-152">Experimental</span></span>|         |
|<span data-ttu-id="b52b8-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="b52b8-153">**Bash**</span></span>      |<span data-ttu-id="b52b8-154">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-154">Experimental</span></span>|         |
|<span data-ttu-id="b52b8-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b52b8-155">**PowerShell**</span></span>|<span data-ttu-id="b52b8-156">Экспериментальный</span><span class="sxs-lookup"><span data-stu-id="b52b8-156">Experimental</span></span>|         |

<span data-ttu-id="b52b8-157">Дополнительные сведения см. в [списке поддерживаемых языков](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="b52b8-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="b52b8-158">Планы службы приложений</span><span class="sxs-lookup"><span data-stu-id="b52b8-158">App service plans</span></span>

<span data-ttu-id="b52b8-159">Функции поддерживаются *планом службы приложений*.</span><span class="sxs-lookup"><span data-stu-id="b52b8-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="b52b8-160">План определяет ресурсы, используемые приложением-функцией.</span><span class="sxs-lookup"><span data-stu-id="b52b8-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="b52b8-161">Можно назначить планы для региона, определить размер и количество используемых виртуальных машин, а также выбрать ценовую категорию.</span><span class="sxs-lookup"><span data-stu-id="b52b8-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="b52b8-162">Для истинного бессерверного подхода в приложениях-функциях может использоваться план **потребления**.</span><span class="sxs-lookup"><span data-stu-id="b52b8-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="b52b8-163">План потребления будет автоматически масштабировать серверную часть в зависимости от нагрузки.</span><span class="sxs-lookup"><span data-stu-id="b52b8-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="b52b8-164">Обзор планов Службы приложений Azure см. в [этой статье](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="b52b8-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="b52b8-165">Создание первой функции</span><span class="sxs-lookup"><span data-stu-id="b52b8-165">Create your first function</span></span>

<span data-ttu-id="b52b8-166">Существует три стандартных способа создания приложений-функций.</span><span class="sxs-lookup"><span data-stu-id="b52b8-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="b52b8-167">Создание скриптов для функций на портале.</span><span class="sxs-lookup"><span data-stu-id="b52b8-167">Script functions in the portal.</span></span>
- <span data-ttu-id="b52b8-168">Создание необходимых ресурсов с помощью интерфейса командной строки Azure (CLI).</span><span class="sxs-lookup"><span data-stu-id="b52b8-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
- <span data-ttu-id="b52b8-169">Создание функций локально с помощью избранной интегрированной среды разработки и их публикация в Azure.</span><span class="sxs-lookup"><span data-stu-id="b52b8-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="b52b8-170">Дополнительные сведения о создании функции с помощью скрипта на портале см. в статье [Создание первой функции на портале Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="b52b8-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="b52b8-171">Чтобы выполнить сборку с помощью Azure CLI, ознакомьтесь со статьей [Краткое руководство. Создание первой функции из командной строки с помощью Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="b52b8-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="b52b8-172">Сведения о создании функции из Visual Studio см. в статье [Создание первой функции с помощью Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b52b8-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="b52b8-173">Общие сведения о триггерах и привязках</span><span class="sxs-lookup"><span data-stu-id="b52b8-173">Understand triggers and bindings</span></span>

<span data-ttu-id="b52b8-174">Функции вызываются *триггером* и могут иметь только один триггер.</span><span class="sxs-lookup"><span data-stu-id="b52b8-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="b52b8-175">Помимо вызова функции определенные триггеры также выступают в качестве привязок.</span><span class="sxs-lookup"><span data-stu-id="b52b8-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="b52b8-176">В дополнение к триггеру можно также определить несколько привязок.</span><span class="sxs-lookup"><span data-stu-id="b52b8-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="b52b8-177">*Привязки* предоставляют декларативный способ подключения данных к коду.</span><span class="sxs-lookup"><span data-stu-id="b52b8-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="b52b8-178">Они могут передаваться (входные) или получать данные (выходные).</span><span class="sxs-lookup"><span data-stu-id="b52b8-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="b52b8-179">Триггеры и привязки упрощают работу с функциями.</span><span class="sxs-lookup"><span data-stu-id="b52b8-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="b52b8-180">Привязки устраняют затраты на создание подключения к базе данных или файловой системе вручную.</span><span class="sxs-lookup"><span data-stu-id="b52b8-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="b52b8-181">Вся информация, необходимая для привязок, содержится в специальном файле *functions.JSON* для скриптов или объявляется с атрибутами в коде.</span><span class="sxs-lookup"><span data-stu-id="b52b8-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="b52b8-182">Некоторые распространенные триггеры:</span><span class="sxs-lookup"><span data-stu-id="b52b8-182">Some common triggers include:</span></span>

- <span data-ttu-id="b52b8-183">хранилище BLOB-объектов: вызов функции, когда файл или папка передаются или изменяются в хранилище;</span><span class="sxs-lookup"><span data-stu-id="b52b8-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="b52b8-184">HTTP: вызов функции, например REST API;</span><span class="sxs-lookup"><span data-stu-id="b52b8-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="b52b8-185">очередь: вызов функции при наличии элементов в очереди;</span><span class="sxs-lookup"><span data-stu-id="b52b8-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="b52b8-186">таймер: вызов функции регулярно.</span><span class="sxs-lookup"><span data-stu-id="b52b8-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="b52b8-187">Примеры привязок:</span><span class="sxs-lookup"><span data-stu-id="b52b8-187">Examples of bindings include:</span></span>

- <span data-ttu-id="b52b8-188">CosmosDB: простое подключение к базе данных для передачи или сохранения файлов;</span><span class="sxs-lookup"><span data-stu-id="b52b8-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="b52b8-189">Хранилище таблиц: работа с хранилищем пар "ключ — значение" из приложения-функции;</span><span class="sxs-lookup"><span data-stu-id="b52b8-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="b52b8-190">Хранилище очередей: простое извлечение элементов из очереди или размещение новых элементов в очереди.</span><span class="sxs-lookup"><span data-stu-id="b52b8-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="b52b8-191">В следующем примере файла *functions.JSON* определены триггер и привязка:</span><span class="sxs-lookup"><span data-stu-id="b52b8-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="b52b8-192">В этом примере функция активируется в результате внесения изменения в хранилище BLOB-объектов в контейнере `images`.</span><span class="sxs-lookup"><span data-stu-id="b52b8-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="b52b8-193">Для файла передается информация, поэтому триггер также выступает в качестве привязки.</span><span class="sxs-lookup"><span data-stu-id="b52b8-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="b52b8-194">Существует другая привязка для размещения информации в очереди с именем `images`.</span><span class="sxs-lookup"><span data-stu-id="b52b8-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="b52b8-195">Ниже приведен скрипт C# для функции.</span><span class="sxs-lookup"><span data-stu-id="b52b8-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="b52b8-196">Этот пример представляет собой простую функцию, которая принимает имя файла, который был изменен или передан в хранилище BLOB-объектов, и помещает его в очередь для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="b52b8-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="b52b8-197">Полный список триггеров и привязок Функций Azure см. в [этой статье](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="b52b8-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="b52b8-198">Прокси-элементы</span><span class="sxs-lookup"><span data-stu-id="b52b8-198">Proxies</span></span>

<span data-ttu-id="b52b8-199">Прокси-серверы обеспечивают функции перенаправления для приложения.</span><span class="sxs-lookup"><span data-stu-id="b52b8-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="b52b8-200">Они предоставляют конечную точку и сопоставляют ее с другим ресурсом.</span><span class="sxs-lookup"><span data-stu-id="b52b8-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="b52b8-201">С помощью прокси-серверов вы можете:</span><span class="sxs-lookup"><span data-stu-id="b52b8-201">With proxies, you can:</span></span>

- <span data-ttu-id="b52b8-202">Перенаправлять входящий запрос на другую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="b52b8-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="b52b8-203">Изменять входящий запрос, прежде чем он будет передан.</span><span class="sxs-lookup"><span data-stu-id="b52b8-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="b52b8-204">Изменять или предоставлять ответ.</span><span class="sxs-lookup"><span data-stu-id="b52b8-204">Modify or provide a response.</span></span>

<span data-ttu-id="b52b8-205">Прокси-серверы используются в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="b52b8-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="b52b8-206">Упрощение, сокращение или изменение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b52b8-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="b52b8-207">Обеспечение единообразного префикса API для нескольких серверных служб.</span><span class="sxs-lookup"><span data-stu-id="b52b8-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="b52b8-208">Имитация ответа на разрабатываемую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="b52b8-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="b52b8-209">Предоставление статического ответа на хорошо известную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="b52b8-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="b52b8-210">Поддержание согласованности конечной точки API во время перемещения или переноса серверной части.</span><span class="sxs-lookup"><span data-stu-id="b52b8-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="b52b8-211">Прокси-серверы хранятся как определения JSON.</span><span class="sxs-lookup"><span data-stu-id="b52b8-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="b52b8-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="b52b8-212">Here is an example:</span></span>

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

<span data-ttu-id="b52b8-213">Прокси-сервер `Domain Redirect` использует сокращенный маршрут и сопоставляет его с более длинным ресурсом функции.</span><span class="sxs-lookup"><span data-stu-id="b52b8-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="b52b8-214">Преобразование выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b52b8-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="b52b8-215">Прокси-сервер `Root` получает все, что отправлено на корневой URL-адрес (`https://--shorturl--/`), и перенаправляет на сайт документации.</span><span class="sxs-lookup"><span data-stu-id="b52b8-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="b52b8-216">Пример использования прокси-серверов показан в видео [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Перенос приложения в облако с помощью бессерверных Функций Azure).</span><span class="sxs-lookup"><span data-stu-id="b52b8-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="b52b8-217">В режиме реального времени приложение ASP.NET Core, работающее на локальном SQL Server, переносится в облако Azure.</span><span class="sxs-lookup"><span data-stu-id="b52b8-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="b52b8-218">Прокси-серверы помогают выполнить рефакторинг традиционного проекта веб-API для использования функций.</span><span class="sxs-lookup"><span data-stu-id="b52b8-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="b52b8-219">Дополнительные сведения о Прокси-серверах Функций Azure см. в [этой статье](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="b52b8-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b52b8-220">[Назад](azure-serverless-platform.md)
>[Вперед](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b52b8-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
