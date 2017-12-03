---
title: "Как создать простую веб-службу WCF HTTP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72e111340fc01df3def2fcb1d5360b00720af2f6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="15e23-102">Как создать простую веб-службу WCF HTTP</span><span class="sxs-lookup"><span data-stu-id="15e23-102">How to: Create a Basic WCF Web HTTP Service</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="15e23-103"> позволяет создать службу, предоставляющую сетевую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="15e23-103"> allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="15e23-104">Сетевые конечные точки отправляют данные в виде XML-кода или JSON, без конверта SOAP.</span><span class="sxs-lookup"><span data-stu-id="15e23-104">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="15e23-105">В этом разделе показано, как предоставить такую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="15e23-105">This topic demonstrates how to expose such an endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15e23-106">Единственный способ защитить сетевую конечную точку заключается в том, чтобы предоставить ее через протокол HTTPS, используя механизм безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="15e23-106">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="15e23-107">Поскольку при использовании безопасности на основе сообщений сведения безопасности обычно помещаются в заголовки SOAP и сообщения, отправляемые другим конечным точкам (не SOAP), не содержат конвертов SOAP, негде разместить данные по безопасности и приходится полагаться на механизм безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="15e23-107">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>  
  
### <a name="to-create-a-web-endpoint"></a><span data-ttu-id="15e23-108">Создание сетевой конечной точки</span><span class="sxs-lookup"><span data-stu-id="15e23-108">To create a Web endpoint</span></span>  
  
1.  <span data-ttu-id="15e23-109">Определите контракт службы с использованием интерфейса, отмеченного атрибутами <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> и <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="15e23-109">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>  
  
     [!code-csharp[htBasicService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="15e23-110">По умолчанию атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> сопоставляет с операцией вызовы POST.</span><span class="sxs-lookup"><span data-stu-id="15e23-110">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="15e23-111">Однако можно указать метод HTTP (например, HEAD, PUT или DELETE) для сопоставления с операцией, задав параметр «method=».</span><span class="sxs-lookup"><span data-stu-id="15e23-111">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="15e23-112">В методе <xref:System.ServiceModel.Web.WebGetAttribute> отсутствует параметр «method=», при этом метод сопоставляет с операцией службы только вызовы GET.</span><span class="sxs-lookup"><span data-stu-id="15e23-112"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>  
  
2.  <span data-ttu-id="15e23-113">Реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="15e23-113">Implement the service contract.</span></span>  
  
     [!code-csharp[htBasicService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="15e23-114">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="15e23-114">To host the service</span></span>  
  
1.  <span data-ttu-id="15e23-115">Создание объекта <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="15e23-115">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htBasicService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]  
  
2.  <span data-ttu-id="15e23-116">Добавьте конечную точку <xref:System.ServiceModel.Description.ServiceEndpoint> с поведением <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="15e23-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
     [!code-csharp[htBasicService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]  
  
    > [!NOTE]
    >  <span data-ttu-id="15e23-117">Если не добавить конечную точку, <xref:System.ServiceModel.Web.WebServiceHost> автоматически создает конечную точку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="15e23-117">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="15e23-118"><xref:System.ServiceModel.Web.WebServiceHost> также добавляет <xref:System.ServiceModel.Description.WebHttpBehavior> и отключает страницу справки HTTP и функцию GET языка описания веб-служб (WSDL), чтобы конечная точка метаданных не мешала конечной точке HTTP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="15e23-118"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>  
    >   
    >  <span data-ttu-id="15e23-119">Добавление конечной точки, не являющейся конечной точкой SOAP, с URL-адресом "" приводит к непредвиденному поведению при попытке вызова операции на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="15e23-119">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="15e23-120">Это обусловлено тем, что URI прослушивания конечной точки совпадает с URI страницы справки (отображаемой в браузере, если ввести в его адресную строку базовый адрес службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="15e23-120">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service).</span></span>  
  
     <span data-ttu-id="15e23-121">Это можно предотвратить любым из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="15e23-121">You can do one of the following actions to prevent this from happening:</span></span>  
  
    -   <span data-ttu-id="15e23-122">Всегда указывать непустой код URI для конечной точки, не являющейся конечной точкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="15e23-122">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>  
  
    -   <span data-ttu-id="15e23-123">Отключить страницу справки.</span><span class="sxs-lookup"><span data-stu-id="15e23-123">Turn off the help page.</span></span> <span data-ttu-id="15e23-124">Это можно сделать с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="15e23-124">This can be done with the following code.</span></span>  
  
     [!code-csharp[htBasicService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]  
  
3.  <span data-ttu-id="15e23-125">Откройте узел службы и подождите, пока пользователь не нажмет клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="15e23-125">Open the service host and wait until the user presses ENTER.</span></span>  
  
     [!code-csharp[htBasicService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]  
  
     <span data-ttu-id="15e23-126">В этом образце показано, как разместить веб-службу с помощью консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="15e23-126">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="15e23-127">Также можно разместить эту службу в IIS.</span><span class="sxs-lookup"><span data-stu-id="15e23-127">You can also host such a service within IIS.</span></span> <span data-ttu-id="15e23-128">Для этого укажите класс <xref:System.ServiceModel.Activation.WebServiceHostFactory> в файле SVC, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="15e23-128">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>  
  
    ```  
          <%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Samples.Service"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory%>  
    ```  
  
### <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="15e23-129">Вызов операций службы, сопоставленных с операцией GET, в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="15e23-129">To call service operations mapped to GET in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="15e23-130">Откройте Internet Explorer и введите «`http://localhost:8000/EchoWithGet?s=Hello, world!`» и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="15e23-130">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="15e23-131">Этот URL-адрес содержит базовый адрес службы ("http://localhost:8000/"), относительный адрес конечной точки (""), вызываемую операцию службы ("EchoWithGet"), вопросительный знак и следующий за ним список именованных параметров, в качестве разделителя между которыми используется амперсанд (&).</span><span class="sxs-lookup"><span data-stu-id="15e23-131">The URL contains the base address of the service ("http://localhost:8000/"), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>  
  
### <a name="to-call-service-operations-in-code"></a><span data-ttu-id="15e23-132">Вызов операции службы в коде.</span><span class="sxs-lookup"><span data-stu-id="15e23-132">To call service operations in code</span></span>  
  
1.  <span data-ttu-id="15e23-133">Создайте экземпляр класса <!--zz <xref:System.ServiceModel.Web.WebChannelFactory>--> `System.ServiceModel.Web.WebChannelFactory` в `using` блока.</span><span class="sxs-lookup"><span data-stu-id="15e23-133">Create an instance of <!--zz <xref:System.ServiceModel.Web.WebChannelFactory>--> `System.ServiceModel.Web.WebChannelFactory` within a `using` block.</span></span>  
  
     [!code-csharp[htBasicService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]  
  
2.  <span data-ttu-id="15e23-134">Добавьте <xref:System.ServiceModel.Description.WebHttpBehavior> в конечную точку, вызываемую объектом <xref:System.ServiceModel.ChannelFactory>.</span><span class="sxs-lookup"><span data-stu-id="15e23-134">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory> calls.</span></span>  
  
     [!code-csharp[htBasicService#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]  
  
3.  <span data-ttu-id="15e23-135">Создайте канал и вызовите службу.</span><span class="sxs-lookup"><span data-stu-id="15e23-135">Create the channel and call the service.</span></span>  
  
     [!code-csharp[htBasicService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]  
  
4.  <span data-ttu-id="15e23-136">Закройте объект <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="15e23-136">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>  
  
     [!code-csharp[htBasicService#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="15e23-137">Пример</span><span class="sxs-lookup"><span data-stu-id="15e23-137">Example</span></span>  
 <span data-ttu-id="15e23-138">Ниже приведен полный код этого примера.</span><span class="sxs-lookup"><span data-stu-id="15e23-138">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htBasicService#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
 [!code-vb[htBasicService#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15e23-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="15e23-139">Compiling the Code</span></span>  
 <span data-ttu-id="15e23-140">При компиляции Service.cs обращается к файлам System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="15e23-140">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e23-141">См. также</span><span class="sxs-lookup"><span data-stu-id="15e23-141">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>  
 <xref:System.ServiceModel.Web.WebInvokeAttribute>  
 <xref:System.ServiceModel.Web.WebServiceHost>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="15e23-142">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="15e23-142">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
