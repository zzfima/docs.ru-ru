---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854818"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="8e953-101">\<Вебскриптендпоинт ></span><span class="sxs-lookup"><span data-stu-id="8e953-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="8e953-102">Этот элемент конфигурации определяет стандартную конечную точку с [ \<](webhttpbinding.md) фиксированной привязкой > WebHttpBinding [ \<](enablewebscript.md) , которая автоматически добавляет енаблевебскрипт поведение >.</span><span class="sxs-lookup"><span data-stu-id="8e953-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="8e953-103">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="8e953-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="8e953-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8e953-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8e953-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8e953-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8e953-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8e953-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8e953-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Вебскриптендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="8e953-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e953-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e953-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e953-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e953-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e953-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e953-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e953-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e953-111">Attributes</span></span>  
  
|<span data-ttu-id="8e953-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e953-112">Attribute</span></span>|<span data-ttu-id="8e953-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8e953-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e953-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8e953-114">webEndpointType</span></span>|<span data-ttu-id="8e953-115">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e953-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e953-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e953-116">Child Elements</span></span>  
 <span data-ttu-id="8e953-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="8e953-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e953-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e953-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8e953-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e953-119">Element</span></span>|<span data-ttu-id="8e953-120">Описание</span><span class="sxs-lookup"><span data-stu-id="8e953-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e953-121">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="8e953-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8e953-122">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="8e953-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e953-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8e953-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
