---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783322"
---
# <a name="persistabletype"></a><span data-ttu-id="deab8-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="deab8-101">\<persistableType></span></span>
<span data-ttu-id="deab8-102">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="deab8-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="deab8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="deab8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="deab8-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="deab8-104">\<comContracts></span></span>  
<span data-ttu-id="deab8-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="deab8-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deab8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="deab8-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="deab8-107">Тип</span><span class="sxs-lookup"><span data-stu-id="deab8-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="deab8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="deab8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="deab8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="deab8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="deab8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="deab8-110">Attributes</span></span>  
  
|<span data-ttu-id="deab8-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="deab8-111">Attribute</span></span>|<span data-ttu-id="deab8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="deab8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="deab8-113">id</span><span class="sxs-lookup"><span data-stu-id="deab8-113">id</span></span>|<span data-ttu-id="deab8-114">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="deab8-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="deab8-115">имя</span><span class="sxs-lookup"><span data-stu-id="deab8-115">name</span></span>|<span data-ttu-id="deab8-116">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="deab8-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="deab8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="deab8-117">Child Elements</span></span>  
 <span data-ttu-id="deab8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="deab8-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="deab8-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="deab8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="deab8-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="deab8-120">Element</span></span>|<span data-ttu-id="deab8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="deab8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="deab8-122">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="deab8-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="deab8-123">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="deab8-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="deab8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="deab8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="deab8-125">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="deab8-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="deab8-126">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="deab8-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="deab8-127">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="deab8-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
