---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 3ea99d360ceb1e3fe6e97cbf9c8827dd7c853f63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256528"
---
# <a name="persistabletype"></a><span data-ttu-id="002b1-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="002b1-101">\<persistableType></span></span>
<span data-ttu-id="002b1-102">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="002b1-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="002b1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="002b1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="002b1-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="002b1-104">\<comContracts></span></span>  
<span data-ttu-id="002b1-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="002b1-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="002b1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="002b1-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="002b1-107">Тип</span><span class="sxs-lookup"><span data-stu-id="002b1-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="002b1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="002b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="002b1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="002b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="002b1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="002b1-110">Attributes</span></span>  
  
|<span data-ttu-id="002b1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="002b1-111">Attribute</span></span>|<span data-ttu-id="002b1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="002b1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="002b1-113">id</span><span class="sxs-lookup"><span data-stu-id="002b1-113">id</span></span>|<span data-ttu-id="002b1-114">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="002b1-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="002b1-115">имя</span><span class="sxs-lookup"><span data-stu-id="002b1-115">name</span></span>|<span data-ttu-id="002b1-116">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="002b1-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="002b1-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="002b1-117">Child Elements</span></span>  
 <span data-ttu-id="002b1-118">Нет</span><span class="sxs-lookup"><span data-stu-id="002b1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="002b1-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="002b1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="002b1-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="002b1-120">Element</span></span>|<span data-ttu-id="002b1-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="002b1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="002b1-122">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="002b1-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="002b1-123">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="002b1-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="002b1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="002b1-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="002b1-125">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="002b1-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="002b1-126">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="002b1-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="002b1-127">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="002b1-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
