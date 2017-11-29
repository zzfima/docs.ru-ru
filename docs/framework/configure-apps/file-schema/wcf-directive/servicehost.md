---
title: '@ServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed64a90131fcd8f2d9f2120c03db4a21d8dc6efe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="b4ebd-101">Связывает фабрику, используемую для создания узла службы, с размещаемой службой и другими элементами программирования, необходимыми для доступа или компиляции кода размещения, представленного в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ebd-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4ebd-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="b4ebd-103">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4ebd-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="b4ebd-104">Служба</span><span class="sxs-lookup"><span data-stu-id="b4ebd-104">Service</span></span>  
 <span data-ttu-id="b4ebd-105">Имя типа CLR размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="b4ebd-106">Это должно быть полное имя типа, который реализует один или несколько контактов службы.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="b4ebd-107">Factory</span><span class="sxs-lookup"><span data-stu-id="b4ebd-107">Factory</span></span>  
 <span data-ttu-id="b4ebd-108">Имя типа CLR фабрики узла службы, используемой для создания узла службы.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="b4ebd-109">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-109">This attribute is optional.</span></span> <span data-ttu-id="b4ebd-110">Если данный атрибут не задан, по умолчанию используется значение <xref:System.ServiceModel.Activation.ServiceHostFactory>, которое возвращает экземпляр <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="b4ebd-111">Отладка</span><span class="sxs-lookup"><span data-stu-id="b4ebd-111">Debug</span></span>  
 <span data-ttu-id="b4ebd-112">Указывает, должна ли служба [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] компилироваться с помощью символов отладки.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-112">Indicates whether the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service should be compiled with debug symbols.</span></span> <span data-ttu-id="b4ebd-113">Если для компиляции службы `true` должны использоваться символы отладки, следует задать значение [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], в противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="b4ebd-114">Язык</span><span class="sxs-lookup"><span data-stu-id="b4ebd-114">Language</span></span>  
 <span data-ttu-id="b4ebd-115">Задает язык, используемый при компиляции всего встроенного кода в файле (SVC).</span><span class="sxs-lookup"><span data-stu-id="b4ebd-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="b4ebd-116">Значения данного атрибута могут представлять любой язык, поддерживаемый .NET, включая C#, VB и JS, что соответствует языкам C#, Visual Basic .NET и JScript .NET.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="b4ebd-117">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="b4ebd-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="b4ebd-118">CodeBehind</span></span>  
 <span data-ttu-id="b4ebd-119">Определяет файл исходного кода, реализующего веб-службу XML, если реализующий ее класс находится в другом файле и не был скомпилирован в сборку и помещен в каталог «\Bin».</span><span class="sxs-lookup"><span data-stu-id="b4ebd-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4ebd-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4ebd-120">Remarks</span></span>  
 <span data-ttu-id="b4ebd-121"><xref:System.ServiceModel.ServiceHost>, используемый для размещения службы, представляет точку расширения в программной модели [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4ebd-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] programming model.</span></span> <span data-ttu-id="b4ebd-122">Для создания узла службы <xref:System.ServiceModel.ServiceHost> используется шаблон фабрики, поскольку он, возможно, имеет полиморфный тип, экземпляр которого среда размещения не должна создавать явно.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="b4ebd-123">В реализации по умолчанию используется фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> для создания экземпляра узла службы <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="b4ebd-124">Но можно предоставить собственную фабрику (той, которая возвращает унаследованный узел), указав имя типа CLR реализации фабрики в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директивы.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="b4ebd-125">Для использования собственной настраиваемой фабрики узла службы вместо фабрики по умолчанию, просто укажите имя типа в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директива следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4ebd-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="b4ebd-126">Создавайте реализацию фабрики в наиболее простом виде.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="b4ebd-127">Если имеется значительный объем пользовательской логики, то можно увеличить возможность повторного использования кода, если разместить эту логику на узле, а не в фабрике.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="b4ebd-128">Например, чтобы включить конечную точку с поддержкой AJAX для `MyService`, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> значение `Factory` атрибута, а не значение по умолчанию <xref:System.ServiceModel.Activation.ServiceHostFactory>в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив как в следующем примере показана.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ebd-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b4ebd-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4ebd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b4ebd-130">See Also</span></span>  
 [<span data-ttu-id="b4ebd-131">Пользовательский узел службы</span><span class="sxs-lookup"><span data-stu-id="b4ebd-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
