---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083742"
---
# <a name="persistabletype"></a><span data-ttu-id="6b4da-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="6b4da-101">\<persistableType></span></span>
<span data-ttu-id="6b4da-102">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="6b4da-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="6b4da-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6b4da-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b4da-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="6b4da-104">\<comContracts></span></span>  
<span data-ttu-id="6b4da-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="6b4da-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4da-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b4da-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="6b4da-107">Тип</span><span class="sxs-lookup"><span data-stu-id="6b4da-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b4da-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6b4da-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b4da-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6b4da-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b4da-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6b4da-110">Attributes</span></span>  
  
|<span data-ttu-id="6b4da-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6b4da-111">Attribute</span></span>|<span data-ttu-id="6b4da-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6b4da-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b4da-113">id</span><span class="sxs-lookup"><span data-stu-id="6b4da-113">id</span></span>|<span data-ttu-id="6b4da-114">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="6b4da-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="6b4da-115">имя</span><span class="sxs-lookup"><span data-stu-id="6b4da-115">name</span></span>|<span data-ttu-id="6b4da-116">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="6b4da-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b4da-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6b4da-117">Child Elements</span></span>  
 <span data-ttu-id="6b4da-118">Нет</span><span class="sxs-lookup"><span data-stu-id="6b4da-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b4da-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6b4da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6b4da-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b4da-120">Element</span></span>|<span data-ttu-id="6b4da-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6b4da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b4da-122">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="6b4da-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="6b4da-123">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="6b4da-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b4da-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6b4da-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="6b4da-125">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="6b4da-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="6b4da-126">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="6b4da-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="6b4da-127">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="6b4da-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
