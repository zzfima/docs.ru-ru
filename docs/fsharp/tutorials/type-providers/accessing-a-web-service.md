---
title: "Пошаговое руководство. доступ к веб-службы с помощью поставщиков типов (F #)"
description: "Сведения об использовании поставщика типов языка описания веб-служб (WSDL), доступные в F # 3.0 для доступа к службе языка WSDL."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="31116-104">Пошаговое руководство. Доступ к веб-службе с помощью поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="31116-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="31116-105">В этом руководстве, была написана для F # 3.0 и будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="31116-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="31116-106">Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="31116-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="31116-107">Справочные ссылки API, вы перейдете MSDN.</span><span class="sxs-lookup"><span data-stu-id="31116-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="31116-108">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="31116-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="31116-109">В этом пошаговом руководстве демонстрируется использование поставщика типов языка описания веб-служб (WSDL), который доступен в F # 3.0 для доступа к службе языка WSDL.</span><span class="sxs-lookup"><span data-stu-id="31116-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="31116-110">В других языках .NET при создании кода для доступа к веб-службы путем вызова svcutil.exe или путем добавления веб-ссылки в, например, C# проекта для получения Visual Studio для вызова svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="31116-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="31116-111">В языке F # имеется дополнительная возможность с помощью поставщика типов WSDL, так как только вы написать код, который создает типов WsdlService, типы создаются и становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="31116-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="31116-112">Этот процесс зависит от службы, будут доступны при написании кода.</span><span class="sxs-lookup"><span data-stu-id="31116-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="31116-113">В данном пошаговом руководстве рассмотрены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="31116-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="31116-114">Необходимо выполнить их в указанном порядке для данного пошагового руководства для успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="31116-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="31116-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="31116-115">Creating the project</span></span>
<br />

- <span data-ttu-id="31116-116">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="31116-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="31116-117">Вызов веб-службы и обработки результатов</span><span class="sxs-lookup"><span data-stu-id="31116-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="31116-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="31116-118">Creating the project</span></span>
<span data-ttu-id="31116-119">На шаге создайте проект и добавляются необходимые ссылки на использование поставщика типов WSDL.</span><span class="sxs-lookup"><span data-stu-id="31116-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="31116-120">Действия для создания и настройки проекта F#</span><span class="sxs-lookup"><span data-stu-id="31116-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="31116-121">Откройте новый проект консольного приложения F #.</span><span class="sxs-lookup"><span data-stu-id="31116-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="31116-122">В **обозревателе решений**, откройте контекстное меню для проекта **ссылки** узел и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="31116-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="31116-123">В **сборки** области, выберите **Framework**, а затем в списке доступных сборок выберите **System.Runtime.Serialization** и  **System.ServiceModel**.</span><span class="sxs-lookup"><span data-stu-id="31116-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="31116-124">В **сборки** области, выберите **расширения**.</span><span class="sxs-lookup"><span data-stu-id="31116-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="31116-125">В списке доступных сборок выберите **FSharp.Data.TypeProviders**, а затем выберите **ОК** кнопку, чтобы добавить ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="31116-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="31116-126">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="31116-126">Configuring the type provider</span></span>
<span data-ttu-id="31116-127">На этом шаге поставщик типов WSDL используется для создания типов для веб-службы TerraServer.</span><span class="sxs-lookup"><span data-stu-id="31116-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="31116-128">Настройка поставщика типов и создание типов</span><span class="sxs-lookup"><span data-stu-id="31116-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="31116-129">Добавьте следующую строку кода, чтобы открыть пространство имен поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="31116-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="31116-130">Добавьте следующую строку кода для вызова поставщик типов с веб-службы.</span><span class="sxs-lookup"><span data-stu-id="31116-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="31116-131">В этом примере используется TerraServer веб-службы.</span><span class="sxs-lookup"><span data-stu-id="31116-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="31116-132">Красная волнистая линия появится под этой строкой кода, если URI службы с ошибкой или если сама служба не работает или не работает.</span><span class="sxs-lookup"><span data-stu-id="31116-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="31116-133">Если навести указатель на код, сообщение об ошибке описание проблемы.</span><span class="sxs-lookup"><span data-stu-id="31116-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="31116-134">Можно получить те же сведения, в **список ошибок** окно или в **окно вывода** после построения.</span><span class="sxs-lookup"><span data-stu-id="31116-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="31116-135">Существует два способа указать параметры конфигурации для подключения к WSDL, с помощью файла app.config проекта или с помощью параметров статический тип в объявлении типа поставщика.</span><span class="sxs-lookup"><span data-stu-id="31116-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="31116-136">Можно использовать svcutil.exe для создания элементов файла соответствующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="31116-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="31116-137">Дополнительные сведения об использовании svcutil.exe для создания сведений о конфигурации для веб-службы см. в разделе [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="31116-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="31116-138">Полное описание параметров статический тип поставщика типов WSDL см. в разделе [поставщика типов WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="31116-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="31116-139">Вызов веб-службы и обработки результатов</span><span class="sxs-lookup"><span data-stu-id="31116-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="31116-140">Каждая веб-служба имеет свой собственный набор типов, которые используются в качестве параметров для вызова его методов.</span><span class="sxs-lookup"><span data-stu-id="31116-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="31116-141">На этом этапе подготовки этих параметров, вызов метода веб- и обработки информации, которую он возвращает.</span><span class="sxs-lookup"><span data-stu-id="31116-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="31116-142">Для вызова веб-службы и обработки результатов</span><span class="sxs-lookup"><span data-stu-id="31116-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="31116-143">Веб-служба может время ожидания или остановке, поэтому вызов веб-службы следует включить в блок обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="31116-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="31116-144">Напишите следующий код для получения данных из веб-службы.</span><span class="sxs-lookup"><span data-stu-id="31116-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="31116-145">Обратите внимание, создаваемые типы данных, которые необходимы для веб-службы, такие как **месте** и **расположение**, как вложенные типы под WsdlService типов **TerraService**.</span><span class="sxs-lookup"><span data-stu-id="31116-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="31116-146">См. также</span><span class="sxs-lookup"><span data-stu-id="31116-146">See Also</span></span>
[<span data-ttu-id="31116-147">Поставщик типов WsdlService</span><span class="sxs-lookup"><span data-stu-id="31116-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="31116-148">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="31116-148">Type Providers</span></span>](index.md)
