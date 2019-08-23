---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933825"
---
# <a name="persistabletype"></a><span data-ttu-id="d1de4-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="d1de4-101">\<persistableType></span></span>
<span data-ttu-id="d1de4-102">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="d1de4-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="d1de4-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d1de4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1de4-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="d1de4-104">\<comContracts></span></span>  
<span data-ttu-id="d1de4-105">\<Комконтракт ></span><span class="sxs-lookup"><span data-stu-id="d1de4-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1de4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1de4-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="d1de4-107">Тип</span><span class="sxs-lookup"><span data-stu-id="d1de4-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1de4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1de4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1de4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1de4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1de4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1de4-110">Attributes</span></span>  
  
|<span data-ttu-id="d1de4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d1de4-111">Attribute</span></span>|<span data-ttu-id="d1de4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d1de4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1de4-113">id</span><span class="sxs-lookup"><span data-stu-id="d1de4-113">id</span></span>|<span data-ttu-id="d1de4-114">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="d1de4-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="d1de4-115">имя</span><span class="sxs-lookup"><span data-stu-id="d1de4-115">name</span></span>|<span data-ttu-id="d1de4-116">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="d1de4-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1de4-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1de4-117">Child Elements</span></span>  
 <span data-ttu-id="d1de4-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="d1de4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1de4-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1de4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d1de4-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1de4-120">Element</span></span>|<span data-ttu-id="d1de4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d1de4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1de4-122">\<Персистаблетипес ></span><span class="sxs-lookup"><span data-stu-id="d1de4-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="d1de4-123">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="d1de4-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1de4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d1de4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="d1de4-125">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="d1de4-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="d1de4-126">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="d1de4-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="d1de4-127">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="d1de4-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
