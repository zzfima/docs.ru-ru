---
title: "Как предоставить доступ к каналу в форматах Atom и RSS"
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
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 66b8ee21159d2900972a9cd8b42a9d26eefb8e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a><span data-ttu-id="80cb3-102">Как предоставить доступ к каналу в форматах Atom и RSS</span><span class="sxs-lookup"><span data-stu-id="80cb3-102">How to: Expose a Feed as Both Atom and RSS</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="80cb3-103"> позволяет создавать службу, предоставляющую веб-канал синдикации.</span><span class="sxs-lookup"><span data-stu-id="80cb3-103"> allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="80cb3-104">В этом разделе рассматривается процесс создания службы синдикации, предоставляющей веб-канал синдикации с помощью Atom 1.0 и RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="80cb3-104">This topic discusses how to create a syndication service that exposes a syndication feed using both Atom 1.0 and RSS 2.0.</span></span> <span data-ttu-id="80cb3-105">Эта служба предоставляет одну конечную точку, которая может вернуть любой формат синдикации.</span><span class="sxs-lookup"><span data-stu-id="80cb3-105">This service exposes one endpoint that can return either syndication format.</span></span> <span data-ttu-id="80cb3-106">В целях упрощения в данном образце используется резидентная служба.</span><span class="sxs-lookup"><span data-stu-id="80cb3-106">For simplicity the service used in this sample is self hosted.</span></span> <span data-ttu-id="80cb3-107">В рабочей среде служба такого типа размещается в IIS или WAS.</span><span class="sxs-lookup"><span data-stu-id="80cb3-107">In a production environment a service of this type would be hosted under IIS or WAS.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="80cb3-108">разные [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] варианты размещения, в разделе [размещения](../../../../docs/framework/wcf/feature-details/hosting.md).</span><span class="sxs-lookup"><span data-stu-id="80cb3-108"> the different [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hosting options, see [Hosting](../../../../docs/framework/wcf/feature-details/hosting.md).</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="80cb3-109">Создание базовой службы синдикации</span><span class="sxs-lookup"><span data-stu-id="80cb3-109">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="80cb3-110">Определите контракт службы с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-110">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="80cb3-111">Каждая операция, предоставляемая как веб-канал синдикации, возвращает объект <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-111">Each operation that is exposed as a syndication feed returns a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> object.</span></span> <span data-ttu-id="80cb3-112">Обратите внимание на параметры для <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-112">Note the parameters for the <xref:System.ServiceModel.Web.WebGetAttribute>.</span></span> <span data-ttu-id="80cb3-113">`UriTemplate` указывает URL-адрес, используемый для вызова этой операции службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-113">`UriTemplate` specifies the URL used to invoke this service operation.</span></span> <span data-ttu-id="80cb3-114">Строка для этого параметра содержит литералы и переменные в фигурных скобках ({*формат*}).</span><span class="sxs-lookup"><span data-stu-id="80cb3-114">The string for this parameter contains literals and a variable in braces ({*format*}).</span></span> <span data-ttu-id="80cb3-115">Эта переменная соответствует параметру `format` операции службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-115">This variable corresponds to the service operation's `format` parameter.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="80cb3-116"> <xref:System.UriTemplate>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-116"> <xref:System.UriTemplate>.</span></span> <span data-ttu-id="80cb3-117">`BodyStyle` влияет на способ записи сообщений, отправляемых и получаемых этой операцией службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-117">`BodyStyle` affects how the messages that this service operation sends and receives are written.</span></span> <span data-ttu-id="80cb3-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> указывает, что данные, отправляемые и получаемые этой операцией службы, не заключаются в оболочку из XML-элементов, определенных в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="80cb3-118"><xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> specifies that the data sent to and from this service operation are not wrapped by infrastructure-defined XML elements.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="80cb3-119"> <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-119"> <xref:System.ServiceModel.Web.WebMessageBodyStyle>.</span></span>  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="80cb3-120">Используйте атрибут <xref:System.ServiceModel.ServiceKnownTypeAttribute>, чтобы задать, какие типы возвращаются операциями службы в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="80cb3-120">Use the <xref:System.ServiceModel.ServiceKnownTypeAttribute> to specify the types that are returned by the service operations in this interface.</span></span>  
  
2.  <span data-ttu-id="80cb3-121">Реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-121">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3.  <span data-ttu-id="80cb3-122">Создайте объект <xref:System.ServiceModel.Syndication.SyndicationFeed>, затем добавьте автора, категорию и описание.</span><span class="sxs-lookup"><span data-stu-id="80cb3-122">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4.  <span data-ttu-id="80cb3-123">Создайте несколько объектов <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-123">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5.  <span data-ttu-id="80cb3-124">Добавьте объекты <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канал.</span><span class="sxs-lookup"><span data-stu-id="80cb3-124">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6.  <span data-ttu-id="80cb3-125">Используйте параметр формата, чтобы был возвращен необходимый формат.</span><span class="sxs-lookup"><span data-stu-id="80cb3-125">Use the format parameter to return the requested format.</span></span>  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="80cb3-126">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="80cb3-126">To host the service</span></span>  
  
1.  <span data-ttu-id="80cb3-127">Создание объекта <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-127">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span> <span data-ttu-id="80cb3-128">Класс <xref:System.ServiceModel.Web.WebServiceHost> автоматически добавляет конечную точку по базовому адресу службы, если конечная точка не указана ни в коде, ни в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="80cb3-128">The <xref:System.ServiceModel.Web.WebServiceHost> class automatically adds an endpoint at the service's base address unless one is specified in code or configuration.</span></span> <span data-ttu-id="80cb3-129">В этом образце конечные точки не указаны, и поэтому предоставляется доступ к конечной точке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="80cb3-129">In this sample, no endpoints are specified so the default endpoint is exposed.</span></span>  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2.  <span data-ttu-id="80cb3-130">Откройте узел службы, загрузите веб-канал из службы, отобразите веб-канал и дождитесь нажатия клавиши ВВОД пользователем.</span><span class="sxs-lookup"><span data-stu-id="80cb3-130">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="80cb3-131">Вызов GetBlog с помощью HTTP GET</span><span class="sxs-lookup"><span data-stu-id="80cb3-131">To call GetBlog with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="80cb3-132">Откройте Internet Explorer, введите следующий URL-адрес и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="80cb3-132">Open Internet Explorer, type the following URL, and press ENTER.</span></span> <span data-ttu-id="80cb3-133">http://localhost:8000/BlogService/GetBlog</span><span class="sxs-lookup"><span data-stu-id="80cb3-133">http://localhost:8000/BlogService/GetBlog</span></span>  
  
     <span data-ttu-id="80cb3-134">URL-адрес содержит базовый адрес службы (http://localhost:8000/BlogService), относительный адрес конечной точки и вызываемую операцию службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-134">The URL contains the base address of the service (http://localhost:8000/BlogService), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="80cb3-135">Вызов GetBlog() из кода</span><span class="sxs-lookup"><span data-stu-id="80cb3-135">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="80cb3-136">Создайте <xref:System.Xml.XmlReader> с базовым адресом и вызываемым методом.</span><span class="sxs-lookup"><span data-stu-id="80cb3-136">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="80cb3-137">Вызовите статический метод <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, передав ему только что созданный объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="80cb3-137">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     <span data-ttu-id="80cb3-138">Это вызывает операцию службы и заполняет новый <xref:System.ServiceModel.Syndication.SyndicationFeed> с помощью модуля форматирования, возвращенного от операции службы.</span><span class="sxs-lookup"><span data-stu-id="80cb3-138">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="80cb3-139">Откройте объект веб-канала.</span><span class="sxs-lookup"><span data-stu-id="80cb3-139">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="80cb3-140">Пример</span><span class="sxs-lookup"><span data-stu-id="80cb3-140">Example</span></span>  
 <span data-ttu-id="80cb3-141">Ниже приведен полный код этого примера.</span><span class="sxs-lookup"><span data-stu-id="80cb3-141">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80cb3-142">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="80cb3-142">Compiling the Code</span></span>  
 <span data-ttu-id="80cb3-143">При компиляции приведенного выше кода задайте ссылки на файлы System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="80cb3-143">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cb3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="80cb3-144">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
