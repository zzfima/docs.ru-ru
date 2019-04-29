---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769737"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="735a1-101">\<webScriptEndpoint ></span><span class="sxs-lookup"><span data-stu-id="735a1-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="735a1-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязка, которая автоматически добавляет [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="735a1-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="735a1-103">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="735a1-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="735a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="735a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="735a1-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="735a1-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735a1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="735a1-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="735a1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="735a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="735a1-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="735a1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="735a1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="735a1-109">Attributes</span></span>  
  
|<span data-ttu-id="735a1-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="735a1-110">Attribute</span></span>|<span data-ttu-id="735a1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="735a1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="735a1-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="735a1-112">webEndpointType</span></span>|<span data-ttu-id="735a1-113">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="735a1-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="735a1-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="735a1-114">Child Elements</span></span>  
 <span data-ttu-id="735a1-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="735a1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="735a1-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="735a1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="735a1-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="735a1-117">Element</span></span>|<span data-ttu-id="735a1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="735a1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="735a1-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="735a1-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="735a1-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="735a1-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="735a1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="735a1-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
