---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3c7da8d5a473b801da8c48d1cb1504b95cc6c769
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342134"
---
# <a name="servicehost"></a><span data-ttu-id="e22e1-101">\@ServiceHost</span><span class="sxs-lookup"><span data-stu-id="e22e1-101">\@ServiceHost</span></span>
<span data-ttu-id="e22e1-102">Связывает фабрику, используемую для создания узла службы, с размещаемой службой и другими элементами программирования, необходимыми для доступа или компиляции кода размещения, представленного в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="e22e1-102">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22e1-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e22e1-103">Syntax</span></span>  
  
```xml  
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```  
  
## <a name="attributes"></a><span data-ttu-id="e22e1-104">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e22e1-104">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="e22e1-105">Service</span><span class="sxs-lookup"><span data-stu-id="e22e1-105">Service</span></span>  
 <span data-ttu-id="e22e1-106">Имя типа CLR размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="e22e1-106">The CLR type name of the service hosted.</span></span> <span data-ttu-id="e22e1-107">Это должно быть полное имя типа, который реализует один или несколько контактов службы.</span><span class="sxs-lookup"><span data-stu-id="e22e1-107">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="e22e1-108">Factory</span><span class="sxs-lookup"><span data-stu-id="e22e1-108">Factory</span></span>  
 <span data-ttu-id="e22e1-109">Имя типа CLR фабрики узла службы, используемой для создания узла службы.</span><span class="sxs-lookup"><span data-stu-id="e22e1-109">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="e22e1-110">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e22e1-110">This attribute is optional.</span></span> <span data-ttu-id="e22e1-111">Если данный атрибут не задан, по умолчанию используется значение <xref:System.ServiceModel.Activation.ServiceHostFactory>, которое возвращает экземпляр <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e22e1-111">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="e22e1-112">Отладка</span><span class="sxs-lookup"><span data-stu-id="e22e1-112">Debug</span></span>  
 <span data-ttu-id="e22e1-113">Указывает, должна ли служба Windows Communication Foundation (WCF) компилироваться с отладочными символами.</span><span class="sxs-lookup"><span data-stu-id="e22e1-113">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="e22e1-114">`true`, если служба WCF должна быть скомпилирована с отладочными символами; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e22e1-114">`true` if the WCF service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="e22e1-115">Language</span><span class="sxs-lookup"><span data-stu-id="e22e1-115">Language</span></span>  
 <span data-ttu-id="e22e1-116">Задает язык, используемый при компиляции всего встроенного кода в файле (SVC).</span><span class="sxs-lookup"><span data-stu-id="e22e1-116">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="e22e1-117">Значения могут представлять любые. NET — поддерживаемый язык, включая `C#`, `VB`и `JS`, которые ссылаются на C#, Visual Basic и JScript .NET соответственно.</span><span class="sxs-lookup"><span data-stu-id="e22e1-117">The values can represent any .NET-supported language, including `C#`, `VB`, and `JS`, which refer to C#, Visual Basic, and JScript .NET, respectively.</span></span> <span data-ttu-id="e22e1-118">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e22e1-118">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="e22e1-119">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="e22e1-119">CodeBehind</span></span>  
 <span data-ttu-id="e22e1-120">Определяет файл исходного кода, реализующего веб-службу XML, если реализующий ее класс находится в другом файле и не был скомпилирован в сборку и помещен в каталог «\Bin».</span><span class="sxs-lookup"><span data-stu-id="e22e1-120">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e22e1-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="e22e1-121">Remarks</span></span>  
 <span data-ttu-id="e22e1-122"><xref:System.ServiceModel.ServiceHost>, используемое для размещения службы, является точкой расширения в модели программирования Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e22e1-122">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="e22e1-123">Для создания узла службы <xref:System.ServiceModel.ServiceHost> используется шаблон фабрики, поскольку он, возможно, имеет полиморфный тип, экземпляр которого среда размещения не должна создавать явно.</span><span class="sxs-lookup"><span data-stu-id="e22e1-123">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="e22e1-124">В реализации по умолчанию используется фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> для создания экземпляра узла службы <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e22e1-124">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e22e1-125">Но вы можете предоставить собственную фабрику (которая возвращает производный узел), указав имя типа CLR для реализации фабрики в директиве [ServiceHost\@](servicehost.md) .</span><span class="sxs-lookup"><span data-stu-id="e22e1-125">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [\@ServiceHost](servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="e22e1-126">Чтобы использовать собственную фабрику узла службы вместо фабрики по умолчанию, просто укажите имя типа в директиве [@ServiceHost](servicehost.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e22e1-126">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="e22e1-127">Создавайте реализацию фабрики в наиболее простом виде.</span><span class="sxs-lookup"><span data-stu-id="e22e1-127">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="e22e1-128">Если имеется значительный объем пользовательской логики, то можно увеличить возможность повторного использования кода, если разместить эту логику на узле, а не в фабрике.</span><span class="sxs-lookup"><span data-stu-id="e22e1-128">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="e22e1-129">Например, чтобы включить конечную точку с поддержкой AJAX для `MyService`, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> для значения атрибута `Factory`, а не <xref:System.ServiceModel.Activation.ServiceHostFactory>по умолчанию в директиве [@ServiceHost](servicehost.md) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e22e1-129">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e22e1-130">Пример</span><span class="sxs-lookup"><span data-stu-id="e22e1-130">Example</span></span>  
  
```xml  
<% @ServiceHost
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e22e1-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e22e1-131">See also</span></span>

- [<span data-ttu-id="e22e1-132">Пользовательский узел службы</span><span class="sxs-lookup"><span data-stu-id="e22e1-132">Custom Service Host</span></span>](../../../wcf/samples/custom-service-host.md)
