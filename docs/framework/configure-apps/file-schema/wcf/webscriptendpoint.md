---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: acafb5b6a5c4911dcf21a55cfb9e93883067e5ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566389"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="0495e-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="0495e-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="0495e-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязка, которая автоматически добавляет [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="0495e-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="0495e-104">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="0495e-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="0495e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0495e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0495e-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0495e-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0495e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0495e-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0495e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0495e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0495e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0495e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0495e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0495e-110">Attributes</span></span>  
  
|<span data-ttu-id="0495e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0495e-111">Attribute</span></span>|<span data-ttu-id="0495e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0495e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0495e-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="0495e-113">webEndpointType</span></span>|<span data-ttu-id="0495e-114">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0495e-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0495e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0495e-115">Child Elements</span></span>  
 <span data-ttu-id="0495e-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0495e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0495e-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0495e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0495e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0495e-118">Element</span></span>|<span data-ttu-id="0495e-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="0495e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0495e-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="0495e-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="0495e-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="0495e-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0495e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0495e-122">See also</span></span>
- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
