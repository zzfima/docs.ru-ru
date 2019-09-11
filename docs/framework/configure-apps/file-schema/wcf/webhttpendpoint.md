---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854798"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="30378-101">\<Вебхттпендпоинт ></span><span class="sxs-lookup"><span data-stu-id="30378-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="30378-102">Этот элемент конфигурации определяет стандартную конечную точку с [ \<](webhttpbinding.md) фиксированной привязкой > WebHttpBinding [ \<](webhttp.md) , которая автоматически добавляет поведение > HTTP.</span><span class="sxs-lookup"><span data-stu-id="30378-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="30378-103">Используйте эту конечную точку при написании службы REST.</span><span class="sxs-lookup"><span data-stu-id="30378-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="30378-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30378-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30378-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="30378-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="30378-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="30378-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="30378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Вебхттпендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="30378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30378-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30378-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30378-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="30378-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30378-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="30378-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30378-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30378-111">Attributes</span></span>  
  
|<span data-ttu-id="30378-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="30378-112">Attribute</span></span>|<span data-ttu-id="30378-113">Описание</span><span class="sxs-lookup"><span data-stu-id="30378-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30378-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="30378-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="30378-115">Логическое значение, указывающее, включен ли автоматический выбор формата.</span><span class="sxs-lookup"><span data-stu-id="30378-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="30378-116">Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.</span><span class="sxs-lookup"><span data-stu-id="30378-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="30378-117">Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30378-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="30378-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="30378-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="30378-119">Атрибут, определяющий формат исходящего ответа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30378-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="30378-120">Это атрибут типа <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="30378-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="30378-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="30378-121">helpEnabled</span></span>|<span data-ttu-id="30378-122">Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="30378-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="30378-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="30378-123">webEndpointType</span></span>|<span data-ttu-id="30378-124">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="30378-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30378-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30378-125">Child Elements</span></span>  
 <span data-ttu-id="30378-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="30378-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30378-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="30378-127">Parent Elements</span></span>  
  
|<span data-ttu-id="30378-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="30378-128">Element</span></span>|<span data-ttu-id="30378-129">Описание</span><span class="sxs-lookup"><span data-stu-id="30378-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30378-130">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="30378-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="30378-131">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="30378-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30378-132">См. также</span><span class="sxs-lookup"><span data-stu-id="30378-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
