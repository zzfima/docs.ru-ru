---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855067"
---
# <a name="persistabletype"></a><span data-ttu-id="87130-101">\<persistableType ></span><span class="sxs-lookup"><span data-stu-id="87130-101">\<persistableType></span></span>
<span data-ttu-id="87130-102">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="87130-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="87130-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87130-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87130-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="87130-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="87130-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="87130-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="87130-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Комконтракт >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="87130-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="87130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Персистаблетипес >** ](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="87130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="87130-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistableType >**</span><span class="sxs-lookup"><span data-stu-id="87130-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87130-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87130-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="87130-110">Тип</span><span class="sxs-lookup"><span data-stu-id="87130-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87130-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87130-111">Attributes and Elements</span></span>  
 <span data-ttu-id="87130-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87130-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87130-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87130-113">Attributes</span></span>  
  
|<span data-ttu-id="87130-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="87130-114">Attribute</span></span>|<span data-ttu-id="87130-115">Описание</span><span class="sxs-lookup"><span data-stu-id="87130-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87130-116">id</span><span class="sxs-lookup"><span data-stu-id="87130-116">id</span></span>|<span data-ttu-id="87130-117">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="87130-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="87130-118">имя</span><span class="sxs-lookup"><span data-stu-id="87130-118">name</span></span>|<span data-ttu-id="87130-119">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="87130-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87130-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87130-120">Child Elements</span></span>  
 <span data-ttu-id="87130-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="87130-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87130-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87130-122">Parent Elements</span></span>  
  
|<span data-ttu-id="87130-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="87130-123">Element</span></span>|<span data-ttu-id="87130-124">Описание</span><span class="sxs-lookup"><span data-stu-id="87130-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87130-125">\<Персистаблетипес ></span><span class="sxs-lookup"><span data-stu-id="87130-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="87130-126">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="87130-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87130-127">См. также</span><span class="sxs-lookup"><span data-stu-id="87130-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="87130-128">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="87130-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="87130-129">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="87130-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="87130-130">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="87130-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
