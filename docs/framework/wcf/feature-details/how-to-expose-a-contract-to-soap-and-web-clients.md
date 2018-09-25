---
title: Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: d82c5e3fc33528eadc3c404cca59a3dcf905e0e2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070532"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="9df0e-102">Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам</span><span class="sxs-lookup"><span data-stu-id="9df0e-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="9df0e-103">По умолчанию Windows Communication Foundation (WCF) делает конечные точки доступными только для клиентов SOAP.</span><span class="sxs-lookup"><span data-stu-id="9df0e-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="9df0e-104">В [как: Создание базовой службы WCF Web HTTP](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), конечной точки становится доступным для клиентов, не использующих протокол SOAP.</span><span class="sxs-lookup"><span data-stu-id="9df0e-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="9df0e-105">Иногда может потребоваться сделать один и тот же контракт доступным обоими способами: в качестве сетевой конечной точки и в качестве конечной точки SOAP.</span><span class="sxs-lookup"><span data-stu-id="9df0e-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="9df0e-106">В данном разделе приводится пример того, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="9df0e-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="9df0e-107">Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="9df0e-107">To define the service contract</span></span>

1. <span data-ttu-id="9df0e-108">Определите контракт службы, с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> и <xref:System.ServiceModel.Web.WebGetAttribute> атрибуты, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="9df0e-109">По умолчанию атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> сопоставляет с операцией вызовы POST.</span><span class="sxs-lookup"><span data-stu-id="9df0e-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="9df0e-110">Однако можно указать метод для сопоставления с операцией, задав параметр «method=».</span><span class="sxs-lookup"><span data-stu-id="9df0e-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="9df0e-111">В методе <xref:System.ServiceModel.Web.WebGetAttribute> отсутствует параметр «method=», при этом метод сопоставляет с операцией службы только вызовы GET.</span><span class="sxs-lookup"><span data-stu-id="9df0e-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="9df0e-112">Реализуйте контракт службы, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="9df0e-113">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="9df0e-113">To host the service</span></span>

1. <span data-ttu-id="9df0e-114">Создание <xref:System.ServiceModel.ServiceHost> объекта, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="9df0e-115">Добавить <xref:System.ServiceModel.Description.ServiceEndpoint> с <xref:System.ServiceModel.BasicHttpBinding> для конечной точки SOAP, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="9df0e-116">Добавить <xref:System.ServiceModel.Description.ServiceEndpoint> с <xref:System.ServiceModel.WebHttpBinding> для конечной точки, не использующих протокол SOAP и добавьте <xref:System.ServiceModel.Description.WebHttpBehavior> к конечной точке, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="9df0e-117">Вызовите `Open()` на <xref:System.ServiceModel.ServiceHost> экземпляра, чтобы открыть узел службы, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9df0e-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="9df0e-118">Вызов операций службы, сопоставленных с операцией GET, в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9df0e-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="9df0e-119">Откройте Internet Explorer и введите "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9df0e-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="9df0e-120">URL-адрес содержит базовый адрес службы (`http://localhost:8000/`), относительный адрес конечной точки ("»), операции службы, чтобы вызов («EchoWithGet») и вопросительный знак и список именованных параметров, разделяемых амперсандом (&).</span><span class="sxs-lookup"><span data-stu-id="9df0e-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="9df0e-121">Вызов операций службы в сетевой конечной точке в коде</span><span class="sxs-lookup"><span data-stu-id="9df0e-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="9df0e-122">Создайте экземпляр класса <xref:System.ServiceModel.Web.WebChannelFactory%601> в блоке `using`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9df0e-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="9df0e-123">Метод `Close()` автоматически вызывается для канала в конце блока `using`.</span><span class="sxs-lookup"><span data-stu-id="9df0e-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="9df0e-124">Создайте канал и вызовите службу, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9df0e-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="9df0e-125">Вызов операций службы в конечной точке SOAP</span><span class="sxs-lookup"><span data-stu-id="9df0e-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="9df0e-126">Создайте экземпляр класса <xref:System.ServiceModel.ChannelFactory> в блоке `using`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9df0e-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="9df0e-127">Создайте канал и вызовите службу, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9df0e-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="9df0e-128">Закрытие узла службы</span><span class="sxs-lookup"><span data-stu-id="9df0e-128">To close the service host</span></span>

1. <span data-ttu-id="9df0e-129">Закройте ведущее приложение службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="9df0e-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="9df0e-130">Пример</span><span class="sxs-lookup"><span data-stu-id="9df0e-130">Example</span></span>

<span data-ttu-id="9df0e-131">Ниже приведен полный код для этого раздела:</span><span class="sxs-lookup"><span data-stu-id="9df0e-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="9df0e-132">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9df0e-132">Compiling the code</span></span>

 <span data-ttu-id="9df0e-133">При компиляции Service.cs обращается к файлам System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="9df0e-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="9df0e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9df0e-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="9df0e-135">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="9df0e-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)