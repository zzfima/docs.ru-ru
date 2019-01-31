---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 3d95624c82388ed6219fc567dd2d3c17bedad7a1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255293"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="5cf00-101">\<webScriptEndpoint ></span><span class="sxs-lookup"><span data-stu-id="5cf00-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="5cf00-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязка, которая автоматически добавляет [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="5cf00-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="5cf00-103">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="5cf00-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="5cf00-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5cf00-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cf00-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5cf00-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf00-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cf00-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cf00-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5cf00-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5cf00-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5cf00-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cf00-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cf00-109">Attributes</span></span>  
  
|<span data-ttu-id="5cf00-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5cf00-110">Attribute</span></span>|<span data-ttu-id="5cf00-111">Описание</span><span class="sxs-lookup"><span data-stu-id="5cf00-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cf00-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="5cf00-112">webEndpointType</span></span>|<span data-ttu-id="5cf00-113">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5cf00-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cf00-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5cf00-114">Child Elements</span></span>  
 <span data-ttu-id="5cf00-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5cf00-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cf00-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5cf00-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5cf00-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cf00-117">Element</span></span>|<span data-ttu-id="5cf00-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="5cf00-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cf00-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5cf00-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5cf00-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="5cf00-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cf00-121">См. также</span><span class="sxs-lookup"><span data-stu-id="5cf00-121">See also</span></span>
- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
