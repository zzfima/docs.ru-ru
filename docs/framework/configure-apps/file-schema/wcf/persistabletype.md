---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: b9d61a736a2f8650c543433931d57e156d115018
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706856"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="da2f9-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="da2f9-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="da2f9-103">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="da2f9-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="da2f9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da2f9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da2f9-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="da2f9-105">\<comContracts></span></span>  
<span data-ttu-id="da2f9-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="da2f9-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2f9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da2f9-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="da2f9-108">Тип</span><span class="sxs-lookup"><span data-stu-id="da2f9-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da2f9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da2f9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="da2f9-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da2f9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da2f9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da2f9-111">Attributes</span></span>  
  
|<span data-ttu-id="da2f9-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da2f9-112">Attribute</span></span>|<span data-ttu-id="da2f9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="da2f9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da2f9-114">id</span><span class="sxs-lookup"><span data-stu-id="da2f9-114">id</span></span>|<span data-ttu-id="da2f9-115">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="da2f9-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="da2f9-116">имя</span><span class="sxs-lookup"><span data-stu-id="da2f9-116">name</span></span>|<span data-ttu-id="da2f9-117">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="da2f9-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da2f9-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da2f9-118">Child Elements</span></span>  
 <span data-ttu-id="da2f9-119">Нет</span><span class="sxs-lookup"><span data-stu-id="da2f9-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da2f9-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da2f9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="da2f9-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="da2f9-121">Element</span></span>|<span data-ttu-id="da2f9-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="da2f9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da2f9-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="da2f9-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="da2f9-124">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="da2f9-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da2f9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="da2f9-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="da2f9-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="da2f9-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="da2f9-127">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="da2f9-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="da2f9-128">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="da2f9-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
