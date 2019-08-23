---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940407"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="1e7d8-101">\<Вебскриптендпоинт ></span><span class="sxs-lookup"><span data-stu-id="1e7d8-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="1e7d8-102">Этот элемент конфигурации определяет стандартную конечную точку с [ \<](webhttpbinding.md) фиксированной привязкой > WebHttpBinding [ \<](enablewebscript.md) , которая автоматически добавляет енаблевебскрипт поведение >.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="1e7d8-103">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="1e7d8-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e7d8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e7d8-105">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="1e7d8-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7d8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e7d8-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e7d8-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e7d8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1e7d8-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e7d8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e7d8-109">Attributes</span></span>  
  
|<span data-ttu-id="1e7d8-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e7d8-110">Attribute</span></span>|<span data-ttu-id="1e7d8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1e7d8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e7d8-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="1e7d8-112">webEndpointType</span></span>|<span data-ttu-id="1e7d8-113">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e7d8-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e7d8-114">Child Elements</span></span>  
 <span data-ttu-id="1e7d8-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e7d8-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e7d8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1e7d8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e7d8-117">Element</span></span>|<span data-ttu-id="1e7d8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1e7d8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e7d8-119">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="1e7d8-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1e7d8-120">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="1e7d8-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e7d8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1e7d8-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
