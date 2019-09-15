---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 1fc85838d7491f94b8da1e0ab458d6d021cd2b32
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989780"
---
# <a name="jsonp"></a><span data-ttu-id="13e62-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="13e62-102">JSONP</span></span>
<span data-ttu-id="13e62-103">В этом образце показано, как обеспечить поддержку JSONP(JSON with Padding) в службах WCF REST.</span><span class="sxs-lookup"><span data-stu-id="13e62-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="13e62-104">JSONP является правилом, используемым для вызова скриптов между доменами путем создания тегов скриптов в текущем документе.</span><span class="sxs-lookup"><span data-stu-id="13e62-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="13e62-105">Результат возвращается в заданной функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="13e62-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="13e62-106">JSONP основан на идее того, что теги, такие `<script src="http://..." >` как, могут оценивать сценарии из любого домена, а скрипт, полученный этими тегами, вычисляется в области, в которой уже могут быть определены другие функции.</span><span class="sxs-lookup"><span data-stu-id="13e62-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="13e62-107">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="13e62-107">Demonstrates</span></span>
 <span data-ttu-id="13e62-108">Междоменная работа со скриптами с JSONP.</span><span class="sxs-lookup"><span data-stu-id="13e62-108">Cross-domain scripting with JSONP.</span></span>

## <a name="discussion"></a><span data-ttu-id="13e62-109">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="13e62-109">Discussion</span></span>
 <span data-ttu-id="13e62-110">В образец входит веб-страница, которая динамически добавляет блок скрипта после отображения страницы в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="13e62-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="13e62-111">В этом блоке скрипта вызывается служба WCF REST, содержащая одну операцию `GetCustomer`.</span><span class="sxs-lookup"><span data-stu-id="13e62-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="13e62-112">Служба WCF REST возвращает имя и адрес клиента, заключенные в оболочку функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="13e62-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="13e62-113">Когда служба WCF REST отправляет ответ, вызывается функция обратного вызова на веб-странице с данными о клиенте, и функция обратного вызова выводит эти данные на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="13e62-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="13e62-114">Вставка тега скрипта и выполнение функции обратного вызова автоматически обрабатываются элементом управления ASP.NET AJAX ScriptManager.</span><span class="sxs-lookup"><span data-stu-id="13e62-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="13e62-115">Схема использования та же, что и для всех прокси ASP.NET AJAX, плюс добавляется строка для включения JSONP, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="13e62-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 <span data-ttu-id="13e62-116">Веб-страница может вызывать службу WCF REST, поскольку эта служба использует объект <xref:System.ServiceModel.Description.WebScriptEndpoint>, где свойство `crossDomainScriptAccessEnabled` установлено в значении `true`.</span><span class="sxs-lookup"><span data-stu-id="13e62-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="13e62-117">Обе эти конфигурации выполняются в файле \<Web. config в элементе System. ServiceModel >.</span><span class="sxs-lookup"><span data-stu-id="13e62-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 <span data-ttu-id="13e62-118">ScriptManager управляет взаимодействием со службой и устраняет сложности реализации доступа JSONP вручную.</span><span class="sxs-lookup"><span data-stu-id="13e62-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="13e62-119">Если `crossDomainScriptAccessEnabled` параметр имеет `true` значение и формат ответа для операции — JSON, инфраструктура WCF проверяет URI запроса на наличие параметра строки запроса обратного вызова и заключает ответ JSON в значение строки запроса обратного вызова. параметр.</span><span class="sxs-lookup"><span data-stu-id="13e62-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="13e62-120">В образце веб-страница вызывает службу WCF REST со следующим URI.</span><span class="sxs-lookup"><span data-stu-id="13e62-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 <span data-ttu-id="13e62-121">Поскольку строковый параметр запроса обратного вызова имеет значение `JsonPCallback`, служба WCF возвращает ответ JSONP, показанный в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="13e62-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 <span data-ttu-id="13e62-122">Этот ответ JSONP содержит данные о клиенте в формате JSON, заключенные в имя функции обратного вызова, запрошенной веб-страницей.</span><span class="sxs-lookup"><span data-stu-id="13e62-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="13e62-123">ScriptManager будет выполнять этот обратный вызов, используя тег скрипта для междоменного запроса, а затем передаст результат в обработчик onSuccess, который передан в операцию GetCustomer прокси ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="13e62-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>

 <span data-ttu-id="13e62-124">Пример состоит из двух веб-приложений ASP.NET: один содержит только службу WCF, а другой — веб-страницу. aspx, которая вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="13e62-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="13e62-125">При запуске решения Visual Studio 2012 будет размещать два веб-сайта на разных портах, что создает среду, в которой служба и клиент находятся в разных доменах.</span><span class="sxs-lookup"><span data-stu-id="13e62-125">When running the solution, Visual Studio 2012 will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13e62-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13e62-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13e62-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="13e62-127">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="13e62-128">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры.</span><span class="sxs-lookup"><span data-stu-id="13e62-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13e62-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="13e62-129">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="13e62-130">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="13e62-130">To run the sample</span></span>  
  
1. <span data-ttu-id="13e62-131">Откройте решение для образца JSONP.</span><span class="sxs-lookup"><span data-stu-id="13e62-131">Open the solution for the JSONP Sample.</span></span>  
  
2. <span data-ttu-id="13e62-132">Нажмите клавишу F5 `http://localhost:26648/JSONPClientPage.aspx` для запуска в браузере.</span><span class="sxs-lookup"><span data-stu-id="13e62-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3. <span data-ttu-id="13e62-133">Обратите внимание, что после загрузки страницы входные текстовые значения "Name" и "Address" заполняются значениями.</span><span class="sxs-lookup"><span data-stu-id="13e62-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="13e62-134">Эти значения были предоставлены из вызова службы WCF после того, как браузер завершил отрисовку страницы.</span><span class="sxs-lookup"><span data-stu-id="13e62-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>
