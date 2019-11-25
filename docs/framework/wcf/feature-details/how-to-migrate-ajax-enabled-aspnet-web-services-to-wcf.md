---
title: Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 60e3088b9075464176c328af1f52676a69c4990f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976133"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a><span data-ttu-id="b4730-102">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="b4730-102">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="b4730-103">В этом разделе описаны процедуры переноса базовой службы ASP.NET AJAX в эквивалентную службу Windows Communication Foundation (WCF) с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="b4730-103">This topic outlines procedures to migrate a basic ASP.NET AJAX service to an equivalent AJAX-enabled Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="b4730-104">Здесь показано, как создать функционально эквивалентную версию WCF службы ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="b4730-104">It shows how to create a functionally equivalent WCF version of an ASP.NET AJAX service.</span></span> <span data-ttu-id="b4730-105">Затем две службы можно использовать параллельно, или службу WCF можно использовать для замены службы ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="b4730-105">The two services can then be used side by side, or the WCF service can be used to replace the ASP.NET AJAX service.</span></span>

 <span data-ttu-id="b4730-106">Перенос существующей службы AJAX ASP.NET в службу WCF AJAX предоставляет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="b4730-106">Migrating an existing ASP.NET AJAX service to a WCF AJAX service gives you the following benefits:</span></span>

- <span data-ttu-id="b4730-107">службу AJAX можно сделать доступной в качестве службы SOAP при минимальной дополнительной настройке;</span><span class="sxs-lookup"><span data-stu-id="b4730-107">You can expose your AJAX service as a SOAP service with minimal extra configuration.</span></span>

- <span data-ttu-id="b4730-108">Вы можете воспользоваться преимуществами таких функций WCF, как трассировка и т. д.</span><span class="sxs-lookup"><span data-stu-id="b4730-108">You can benefit from WCF features such as tracing, and so on.</span></span>

 <span data-ttu-id="b4730-109">В следующих процедурах предполагается, что вы используете Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b4730-109">The following procedures assume that you are using Visual Studio 2012.</span></span>

 <span data-ttu-id="b4730-110">Код, получаемый в результате применения описанных в этом разделе процедур, приведен в примере после процедур.</span><span class="sxs-lookup"><span data-stu-id="b4730-110">The code that results from the procedures outlined in this topic is provided in the example following the procedures.</span></span>

 <span data-ttu-id="b4730-111">Дополнительные сведения о предоставлении службы WCF через конечную точку с поддержкой AJAX см. в разделе [Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) .</span><span class="sxs-lookup"><span data-stu-id="b4730-111">For more information about exposing a WCF service through an AJAX-enabled endpoint, see the [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) topic.</span></span>

### <a name="to-create-and-test-the-aspnet-web-service-application"></a><span data-ttu-id="b4730-112">Создание и тестирование приложения веб-службы ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4730-112">To create and test the ASP.NET Web service application</span></span>

1. <span data-ttu-id="b4730-113">Откройте Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b4730-113">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="b4730-114">В меню **файл** выберите **создать**, затем **проект**, **веб**, а затем выберите **ASP.NET веб-служба приложение**.</span><span class="sxs-lookup"><span data-stu-id="b4730-114">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Service Application**.</span></span>

3. <span data-ttu-id="b4730-115">Присвойте проекту имя `ASPHello` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b4730-115">Name the project `ASPHello` and click **OK**.</span></span>

4. <span data-ttu-id="b4730-116">В файле Service1.asmx.cs снимите знаки комментария со строки, содержащей `System.Web.Script.Services.ScriptService]`, чтобы включить для этой службы поддержку AJAX.</span><span class="sxs-lookup"><span data-stu-id="b4730-116">Uncomment the line in the Service1.asmx.cs file that contains `System.Web.Script.Services.ScriptService]` to enable AJAX for this service.</span></span>

5. <span data-ttu-id="b4730-117">В меню **Сборка** выберите пункт **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="b4730-117">From the **Build** menu, select **Build Solution**.</span></span>

6. <span data-ttu-id="b4730-118">В меню **Отладка** выберите пункт **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="b4730-118">From the **Debug** menu, select **Start Without Debugging**.</span></span>

7. <span data-ttu-id="b4730-119">На созданной веб-странице выберите операцию `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="b4730-119">On the Web page generated, select the `HelloWorld` operation.</span></span>

8. <span data-ttu-id="b4730-120">Нажмите кнопку **Invoke (вызвать** ) на странице теста `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="b4730-120">Click the **Invoke** button on the `HelloWorld` test page.</span></span> <span data-ttu-id="b4730-121">Должен появиться следующий XML-ответ.</span><span class="sxs-lookup"><span data-stu-id="b4730-121">You should receive the following XML response.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. <span data-ttu-id="b4730-122">Этот ответ подтверждает, что имеется функционирующая служба AJAX ASP.NET, и что эта служба доступна через конечную точку Service1.asmx/HelloWorld, которая отвечает на запросы HTTP POST и возвращает XML-код.</span><span class="sxs-lookup"><span data-stu-id="b4730-122">This response confirms that you now have a functioning ASP.NET AJAX service and, in particular, that the service has now exposed an endpoint at Service1.asmx/HelloWorld that responds to HTTP POST requests and returns XML.</span></span>

     <span data-ttu-id="b4730-123">Теперь все готово для преобразования этой службы для использования службы WCF AJAX.</span><span class="sxs-lookup"><span data-stu-id="b4730-123">Now you are ready to convert this service to use a WCF AJAX service.</span></span>

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a><span data-ttu-id="b4730-124">Создание эквивалентного приложения службы AJAX WCF</span><span class="sxs-lookup"><span data-stu-id="b4730-124">To create an equivalent WCF AJAX service application</span></span>

1. <span data-ttu-id="b4730-125">Щелкните правой кнопкой мыши проект **асфелло** и выберите **Добавить**, затем **новый элемент**и **Служба WCF с поддержкой AJAX**.</span><span class="sxs-lookup"><span data-stu-id="b4730-125">Right-click the **ASPHello** project and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>

2. <span data-ttu-id="b4730-126">Присвойте службе имя `WCFHello` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b4730-126">Name the service `WCFHello` and click **Add**.</span></span>

3. <span data-ttu-id="b4730-127">Откройте файл WCFHello.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="b4730-127">Open the WCFHello.svc.cs file.</span></span>

4. <span data-ttu-id="b4730-128">В Service1.asmx.cs скопируйте следующую реализацию операции `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="b4730-128">From Service1.asmx.cs, copy the following implementation of the `HelloWorld` operation.</span></span>

    ```csharp
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

5. <span data-ttu-id="b4730-129">Вставьте скопированную реализацию `HelloWorld` операции в файл WCFHello.svc.cs вместо следующего кода.</span><span class="sxs-lookup"><span data-stu-id="b4730-129">Paste to copied implementation of the `HelloWorld` operation into the WCFHello.svc.cs file in place of the following code.</span></span>

    ```csharp
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. <span data-ttu-id="b4730-130">Укажите `Namespace` атрибут <xref:System.ServiceModel.ServiceContractAttribute> как `WCFHello`.</span><span class="sxs-lookup"><span data-stu-id="b4730-130">Specify the `Namespace` attribute for <xref:System.ServiceModel.ServiceContractAttribute> as `WCFHello`.</span></span>

    ```csharp
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. <span data-ttu-id="b4730-131">Добавьте <xref:System.ServiceModel.Web.WebInvokeAttribute> в `HelloWorld` операцию и присвойте свойству <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> значение, возвращающее <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span><span class="sxs-lookup"><span data-stu-id="b4730-131">Add the <xref:System.ServiceModel.Web.WebInvokeAttribute> to the `HelloWorld` operation and set the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> property to return <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span></span> <span data-ttu-id="b4730-132">Обратите внимание, что если это свойство не задано, будет возвращаться тип <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span><span class="sxs-lookup"><span data-stu-id="b4730-132">Note that, if not set, the default return type is <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span>

    ```csharp
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. <span data-ttu-id="b4730-133">В меню **Сборка** выберите пункт **построить решение**.</span><span class="sxs-lookup"><span data-stu-id="b4730-133">From the **Build** menu, select **Build Solution**.</span></span>

9. <span data-ttu-id="b4730-134">Откройте файл Вкфхелло. svc и в меню **Отладка** выберите **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="b4730-134">Open the WCFHello.svc file and from the **Debug** menu, select **Start Without Debugging**.</span></span>

10. <span data-ttu-id="b4730-135">Теперь служба предоставляет конечную точку на `WCFHello.svc/HelloWorld`, которая реагирует на HTTP-запросы POST.</span><span class="sxs-lookup"><span data-stu-id="b4730-135">The service now exposes an endpoint at `WCFHello.svc/HelloWorld`, which responds to HTTP POST requests.</span></span> <span data-ttu-id="b4730-136">Запросы HTTP POST невозможно тестировать с помощью браузера, но конечная точка возвращает следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="b4730-136">HTTP POST requests cannot be tested from the browser, but the endpoint returns XML following XML.</span></span>

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. <span data-ttu-id="b4730-137">`WCFHello.svc/HelloWorld` и конечные точки `Service1.aspx/HelloWorld` теперь функционально эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="b4730-137">The `WCFHello.svc/HelloWorld` and the `Service1.aspx/HelloWorld` endpoints are now functionally equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="b4730-138">Пример</span><span class="sxs-lookup"><span data-stu-id="b4730-138">Example</span></span>
 <span data-ttu-id="b4730-139">Код, получаемый в результате применения описанных в этом разделе процедур, приведен в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b4730-139">The code that results from the procedures outlined in this topic is provided in the following example.</span></span>

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 <span data-ttu-id="b4730-140">Тип <xref:System.Xml.XmlDocument> не поддерживается классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, потому что его невозможно сериализовать с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b4730-140">The <xref:System.Xml.XmlDocument> type is not supported by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because it is not serializable by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b4730-141">Можно использовать тип <xref:System.Xml.Linq.XDocument> или сериализовать свойство <xref:System.Xml.XmlDocument.DocumentElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="b4730-141">You can use either an <xref:System.Xml.Linq.XDocument> type, or serialize the <xref:System.Xml.XmlDocument.DocumentElement%2A> instead.</span></span>

 <span data-ttu-id="b4730-142">Если веб-службы ASMX обновляются и мигрируют параллельно службам WCF, Избегайте сопоставления двух типов с одним и тем же именем на клиенте.</span><span class="sxs-lookup"><span data-stu-id="b4730-142">If ASMX Web services are being upgraded and migrated side-by-side to WCF services, avoid mapping two types to the same name on the client.</span></span> <span data-ttu-id="b4730-143">Это приведет к исключению при сериализации, если в атрибутах <xref:System.Web.Services.WebMethodAttribute> и <xref:System.ServiceModel.ServiceContractAttribute> будет использоваться один и тот же тип:</span><span class="sxs-lookup"><span data-stu-id="b4730-143">This causes an exception in serializers if the same type is used in a <xref:System.Web.Services.WebMethodAttribute> and a <xref:System.ServiceModel.ServiceContractAttribute>:</span></span>

- <span data-ttu-id="b4730-144">Если сначала добавляется служба WCF, вызов метода в веб-службе ASMX приводит к возникновению исключения в <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29>, так как определение стиля WCF для порядка в прокси-сервере имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="b4730-144">If WCF service is added first, invoking the method on ASMX Web Service causes exception in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> because the WCF style definition of the order in the proxy takes precedence.</span></span>

- <span data-ttu-id="b4730-145">Если сначала добавляется веб-служба ASMX, вызов метода в службе WCF вызывает исключение в <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, так как определение стиля веб-службы для порядка в прокси-сервере имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="b4730-145">If ASMX Web Service is added first, invoking method on WCF service causes exception in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because the Web Service style definition of the order in the proxy takes precedence.</span></span>

 <span data-ttu-id="b4730-146">Имеются важные различия в работе класса <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и класса <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b4730-146">There are significant differences in behavior between the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> and the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span></span> <span data-ttu-id="b4730-147">Например, класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> представляет словарь в виде массива пар "ключ-значение", а класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET представляет словарь в виде фактических объектов JSON.</span><span class="sxs-lookup"><span data-stu-id="b4730-147">For example, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> represents a dictionary as an array of key/value pairs, whereas the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> represents a dictionary as actual JSON objects.</span></span> <span data-ttu-id="b4730-148">Ниже представлен словарь в формате AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b4730-148">So the following is the dictionary represented in ASP.NET AJAX.</span></span>

```csharp
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 <span data-ttu-id="b4730-149">Этот словарь состоит из объектов JSON, как показано в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="b4730-149">This dictionary is represented in JSON objects as shown in the following list:</span></span>

- <span data-ttu-id="b4730-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span><span class="sxs-lookup"><span data-stu-id="b4730-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span></span>

- <span data-ttu-id="b4730-151">{"One": 1, "два": 2} ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span><span class="sxs-lookup"><span data-stu-id="b4730-151">{"one":1,"two":2} by the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span></span>

 <span data-ttu-id="b4730-152">Класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> обладает более широкими возможностями в том смысле, что он может обрабатываться словари, где тип ключа не является строковым; класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> не поддерживает такой возможности.</span><span class="sxs-lookup"><span data-stu-id="b4730-152">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is more powerful in the sense that it can handle dictionaries where the key type is not string, while the <xref:System.Web.Script.Serialization.JavaScriptSerializer> cannot.</span></span> <span data-ttu-id="b4730-153">Однако последний класс лучше работает с форматом JSON.</span><span class="sxs-lookup"><span data-stu-id="b4730-153">But the latter is more JSON-friendly.</span></span>

 <span data-ttu-id="b4730-154">Ключевые различия между этими сериализаторами показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b4730-154">The significant differences between these serializers are summarized in the following table.</span></span>

|<span data-ttu-id="b4730-155">Категория различий</span><span class="sxs-lookup"><span data-stu-id="b4730-155">Category of Differences</span></span>|<span data-ttu-id="b4730-156">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="b4730-156">DataContractJsonSerializer</span></span>|<span data-ttu-id="b4730-157">JavaScriptSerializer AJAX ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4730-157">ASP.NET AJAX JavaScriptSerializer</span></span>|
|-----------------------------|--------------------------------|---------------------------------------|
|<span data-ttu-id="b4730-158">Десериализация пустого буфера (new byte[0]) в <xref:System.Object> (или <xref:System.Uri>, или некоторые другие классы).</span><span class="sxs-lookup"><span data-stu-id="b4730-158">Deserializing the empty buffer (new byte[0]) into <xref:System.Object> (or <xref:System.Uri>, or some other classes).</span></span>|<span data-ttu-id="b4730-159">SerializationException</span><span class="sxs-lookup"><span data-stu-id="b4730-159">SerializationException</span></span>|<span data-ttu-id="b4730-160">null</span><span class="sxs-lookup"><span data-stu-id="b4730-160">null</span></span>|
|<span data-ttu-id="b4730-161">Сериализация <xref:System.DBNull.Value></span><span class="sxs-lookup"><span data-stu-id="b4730-161">Serialization of <xref:System.DBNull.Value></span></span>|<span data-ttu-id="b4730-162">{} (или {"__type": "#System"})</span><span class="sxs-lookup"><span data-stu-id="b4730-162">{} (or {"__type":"#System"})</span></span>|<span data-ttu-id="b4730-163">Null</span><span class="sxs-lookup"><span data-stu-id="b4730-163">Null</span></span>|
|<span data-ttu-id="b4730-164">Сериализация закрытых членов типов [Serializable]</span><span class="sxs-lookup"><span data-stu-id="b4730-164">Serialization of the private members of [Serializable] types.</span></span>|<span data-ttu-id="b4730-165">Сериализуются</span><span class="sxs-lookup"><span data-stu-id="b4730-165">serialized</span></span>|<span data-ttu-id="b4730-166">Не сериализуются</span><span class="sxs-lookup"><span data-stu-id="b4730-166">not serialized</span></span>|
|<span data-ttu-id="b4730-167">Сериализация открытых свойств типов <xref:System.Runtime.Serialization.ISerializable></span><span class="sxs-lookup"><span data-stu-id="b4730-167">Serialization of the public properties of <xref:System.Runtime.Serialization.ISerializable> types.</span></span>|<span data-ttu-id="b4730-168">Не сериализуются</span><span class="sxs-lookup"><span data-stu-id="b4730-168">not serialized</span></span>|<span data-ttu-id="b4730-169">Сериализуются</span><span class="sxs-lookup"><span data-stu-id="b4730-169">serialized</span></span>|
|<span data-ttu-id="b4730-170">Расширения JSON</span><span class="sxs-lookup"><span data-stu-id="b4730-170">"Extensions" of JSON</span></span>|<span data-ttu-id="b4730-171">Удовлетворяет спецификации JSON, которая требует заключать имена членов объектов в кавычки ({"a":"hello"}).</span><span class="sxs-lookup"><span data-stu-id="b4730-171">Adheres to the JSON specification, which requires quotes on object member names ({"a":"hello"}).</span></span>|<span data-ttu-id="b4730-172">Поддерживает имена членов объектов без кавычек ({a:"hello"}).</span><span class="sxs-lookup"><span data-stu-id="b4730-172">Supports the names of object members without quotes ({a:"hello"}).</span></span>|
|<span data-ttu-id="b4730-173">Время в формате UTC (<xref:System.DateTime>)</span><span class="sxs-lookup"><span data-stu-id="b4730-173"><xref:System.DateTime> Coordinated Universal Time (UTC)</span></span>|<span data-ttu-id="b4730-174">Не поддерживает формат "\\/дате (123456789U)\\/" или "\\/дате\\(\d + (U&#124;(\\+\\-[\d{4}]))?\\)\\\\/) ".</span><span class="sxs-lookup"><span data-stu-id="b4730-174">Does not support format "\\/Date(123456789U)\\/" or "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)".</span></span>|<span data-ttu-id="b4730-175">Поддерживает формат "\\/дате (123456789U)\\/" and "\\/дате\\(\d + (U&#124;(\\+\\-[\d{4}]))?\\)\\\\/) "как значения DateTime.</span><span class="sxs-lookup"><span data-stu-id="b4730-175">Supports format "\\/Date(123456789U)\\/" and "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)" as DateTime values.</span></span>|
|<span data-ttu-id="b4730-176">Представление словарей</span><span class="sxs-lookup"><span data-stu-id="b4730-176">Representation of dictionaries</span></span>|<span data-ttu-id="b4730-177">Массив KeyValuePair\<K, V >, обрабатывает типы ключей, которые не являются строками.</span><span class="sxs-lookup"><span data-stu-id="b4730-177">An array of KeyValuePair\<K,V>, handles key types that are not strings.</span></span>|<span data-ttu-id="b4730-178">Фактические объекты JSON, но обрабатывает только ключи строковых типов</span><span class="sxs-lookup"><span data-stu-id="b4730-178">As actual JSON objects - but only handles key types that are strings.</span></span>|
|<span data-ttu-id="b4730-179">Escape-символы</span><span class="sxs-lookup"><span data-stu-id="b4730-179">Escaped characters</span></span>|<span data-ttu-id="b4730-180">Всегда с escape-символом прямой косой черты (/); нельзя использовать недопустимые символы JSON без escape-символа, например "\n"</span><span class="sxs-lookup"><span data-stu-id="b4730-180">Always with an escape forward slash (/); never allows un-escaped invalid JSON characters, such as "\n".</span></span>|<span data-ttu-id="b4730-181">Значения DateTime с escape-символом прямой косой черты (/)</span><span class="sxs-lookup"><span data-stu-id="b4730-181">With an escape forward slash (/) for DateTime values.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b4730-182">См. также</span><span class="sxs-lookup"><span data-stu-id="b4730-182">See also</span></span>

- [<span data-ttu-id="b4730-183">Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="b4730-183">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
