---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 92c59b3804e22c62340acccc1e12e594203c8e8b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145423"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="73963-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="73963-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="73963-103">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="73963-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="73963-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="73963-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73963-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="73963-105">\<comContracts></span></span>  
<span data-ttu-id="73963-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="73963-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73963-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73963-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="73963-108">Тип</span><span class="sxs-lookup"><span data-stu-id="73963-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73963-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73963-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73963-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73963-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73963-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73963-111">Attributes</span></span>  
  
|<span data-ttu-id="73963-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73963-112">Attribute</span></span>|<span data-ttu-id="73963-113">Описание</span><span class="sxs-lookup"><span data-stu-id="73963-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73963-114">id</span><span class="sxs-lookup"><span data-stu-id="73963-114">id</span></span>|<span data-ttu-id="73963-115">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="73963-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="73963-116">имя</span><span class="sxs-lookup"><span data-stu-id="73963-116">name</span></span>|<span data-ttu-id="73963-117">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="73963-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73963-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73963-118">Child Elements</span></span>  
 <span data-ttu-id="73963-119">Нет</span><span class="sxs-lookup"><span data-stu-id="73963-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73963-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73963-120">Parent Elements</span></span>  
  
|<span data-ttu-id="73963-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="73963-121">Element</span></span>|<span data-ttu-id="73963-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="73963-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73963-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="73963-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="73963-124">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="73963-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73963-125">См. также</span><span class="sxs-lookup"><span data-stu-id="73963-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="73963-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="73963-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="73963-127">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="73963-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="73963-128">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="73963-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
