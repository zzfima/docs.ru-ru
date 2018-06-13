---
title: Инструмент Microsoft WCF Web Service Reference Provider
description: Обзор инструмента Microsoft WCF Web Service Reference Provider, который расширяет функциональные возможности проектов .NET Core и ASP.NET Core аналогично функции "Добавление ссылки на службу" для проектов .NET Framework.
author: mlacouture
ms.author: johalex
ms.date: 04/19/2018
ms.custom: mvc
ms.openlocfilehash: 416ca4dbedcf6e610aa5307c87934c0cb18be749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215382"
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="9a51b-103">Инструмент Microsoft WCF Web Service Reference Provider</span><span class="sxs-lookup"><span data-stu-id="9a51b-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="9a51b-104">В течение многих лет разработчики на Visual Studio оставались довольны той производительностью, которую обеспечивал инструмент [**Добавление ссылки на службу**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference), когда их проектам .NET Framework требовался доступ к веб-службам.</span><span class="sxs-lookup"><span data-stu-id="9a51b-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="9a51b-105">Инструмент **WCF Web Service Reference** представляет собой расширение подключенной службы Visual Studio, предоставляющее такие функции, как "Добавление ссылки на службу", проектам .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9a51b-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="9a51b-106">Инструмент извлекает метаданные веб-службы в текущем решении, в сетевом расположении или из файла WSDL, а затем создает совместимый с .NET Core исходный файл, содержащий прокси-код клиента Windows Communication Foundation (WCF), который можно использовать для доступа к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="9a51b-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a51b-107">Ссылаться на службы следует только из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="9a51b-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="9a51b-108">Добавление ссылок из ненадежного источника может нарушить безопасность.</span><span class="sxs-lookup"><span data-stu-id="9a51b-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9a51b-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9a51b-109">Prerequisites</span></span>

* <span data-ttu-id="9a51b-110">[Visual Studio 2017 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="9a51b-110">[Visual Studio 2017 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) or later versions</span></span>

## <a name="how-to-use-the-extension"></a><span data-ttu-id="9a51b-111">Использование расширения</span><span class="sxs-lookup"><span data-stu-id="9a51b-111">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="9a51b-112">Функция **WCF Web Service Reference** (Ссылка на веб-службу WCF) применима к проектам, созданным с помощью следующих шаблонов проекта:</span><span class="sxs-lookup"><span data-stu-id="9a51b-112">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="9a51b-113">**Visual C#** > **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="9a51b-113">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="9a51b-114">**Visual C#** > **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="9a51b-114">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="9a51b-115">**Visual C#** > **Web** > **Веб-приложение ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="9a51b-115">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="9a51b-116">Эта статья, где в качестве примера используется шаблон проекта **Веб-приложение ASP.NET Core**, описывает добавление ссылки на службу WCF в проект:</span><span class="sxs-lookup"><span data-stu-id="9a51b-116">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="9a51b-117">В обозревателе решений дважды щелкните узел **Подключенные службы** проекта (для проекта .NET Core или .NET Standard этот параметр отображается, если щелкнуть правой кнопкой мыши узел **Зависимости** проекта в обозревателе решений).</span><span class="sxs-lookup"><span data-stu-id="9a51b-117">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="9a51b-118">Отображается страница **Подключенные службы**, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="9a51b-118">The **Connected Services** page appears as shown in the following image:</span></span>

![Вкладка "Подключенные службы"](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="9a51b-120">На странице **Подключенные службы** выберите **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-120">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="9a51b-121">Открывается мастер **Настройка ссылки на веб-службу WCF**:</span><span class="sxs-lookup"><span data-stu-id="9a51b-121">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![Вкладка "Конечная точка службы"](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="9a51b-123">Выберите службу.</span><span class="sxs-lookup"><span data-stu-id="9a51b-123">Select a service.</span></span>

    <span data-ttu-id="9a51b-124">3а.</span><span class="sxs-lookup"><span data-stu-id="9a51b-124">3a.</span></span> <span data-ttu-id="9a51b-125">В мастере **Настройка ссылки на веб-службу WCF** доступно несколько параметров для поиска служб:</span><span class="sxs-lookup"><span data-stu-id="9a51b-125">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="9a51b-126">Чтобы найти службы, определенные в текущем решении, нажмите кнопку **Обнаружение**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-126">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="9a51b-127">Чтобы найти службы, размещенные по указанному адресу, введите URL-адрес службы в поле **Адрес** и нажмите кнопку **Перейти**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-127">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="9a51b-128">Чтобы выбрать WSDL-файл, содержащий информацию о метаданных веб-службы, нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-128">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="9a51b-129">3б.</span><span class="sxs-lookup"><span data-stu-id="9a51b-129">3b.</span></span> <span data-ttu-id="9a51b-130">Выберите службу в списке результатов поиска в поле **Службы**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-130">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="9a51b-131">При необходимости введите пространство имен для сформированного кода в соответствующем текстовом поле **Пространство имен**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-131">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="9a51b-132">3в.</span><span class="sxs-lookup"><span data-stu-id="9a51b-132">3c.</span></span> <span data-ttu-id="9a51b-133">Нажмите кнопку **Далее**, чтобы открыть страницы **Параметры типа данных** и **Параметры клиента**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-133">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="9a51b-134">Можно также нажать кнопку **Готово**, чтобы использовать параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a51b-134">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="9a51b-135">Форма **Параметры типа данных** позволяет уточнить созданные параметры конфигурации для ссылок на службу:</span><span class="sxs-lookup"><span data-stu-id="9a51b-135">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![Вкладка "Параметры типа данных"](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="9a51b-137">Параметр **Повторно использовать типы в сборках, на которые есть ссылки** удобен, когда типы данных, необходимые для создания кода ссылки на службу, определены в одной из сборок, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="9a51b-137">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="9a51b-138">Важно использовать эти существующие типы данных повторно, чтобы избежать конфликта типов во время компиляции или проблем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a51b-138">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="9a51b-139">При загрузке сведений о типах может возникнуть задержка, которая зависит от числа зависимостей проекта и других факторов, связанных с производительностью системы.</span><span class="sxs-lookup"><span data-stu-id="9a51b-139">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="9a51b-140">Кнопка **Готово** во время загрузки недоступна, если только не снят флажок **Повторно использовать типы в сборках, на которые есть ссылки**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-140">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="9a51b-141">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9a51b-141">Click **Finish** when you are done.</span></span>


<span data-ttu-id="9a51b-142">Отображая ход выполнения, инструмент:</span><span class="sxs-lookup"><span data-stu-id="9a51b-142">While displaying progress, the tool:</span></span>

* <span data-ttu-id="9a51b-143">скачивает метаданные из службы WCF;</span><span class="sxs-lookup"><span data-stu-id="9a51b-143">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="9a51b-144">формирует код для ссылок на службы в файле с именем *reference.cs* и добавляет его в узел **Подключенные службы** проекта;</span><span class="sxs-lookup"><span data-stu-id="9a51b-144">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="9a51b-145">обновляет файл проекта (CSPROJ-файл) с использованием ссылок на пакеты NuGet, необходимых для компиляции и запуска на целевой платформе.</span><span class="sxs-lookup"><span data-stu-id="9a51b-145">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Окно хода выполнения](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="9a51b-147">После завершения этих процессов можно создать экземпляр сформированного типа клиента WCF и вызвать операции службы.</span><span class="sxs-lookup"><span data-stu-id="9a51b-147">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a51b-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9a51b-148">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="9a51b-149">Отзывы и вопросы</span><span class="sxs-lookup"><span data-stu-id="9a51b-149">Feedback & questions</span></span>
<span data-ttu-id="9a51b-150">Если у вас появились вопросы или отзывы, [сообщите об этом на сайте GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="9a51b-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="9a51b-151">Вы также можете просмотреть имеющиеся вопросы или проблемы [в репозитории WCF на сайте GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="9a51b-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="9a51b-152">заметки о выпуске;</span><span class="sxs-lookup"><span data-stu-id="9a51b-152">Release notes</span></span>
* <span data-ttu-id="9a51b-153">Актуальные сведения о выпуске, включая описание известных проблем, см. в [заметках о выпуске](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md).</span><span class="sxs-lookup"><span data-stu-id="9a51b-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 
