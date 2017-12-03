---
title: "&lt;Восстанавливаемый тип persistableType&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56443902885e191d93897096e55742f7665ba00a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="7a35c-102">&lt;Восстанавливаемый тип persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="7a35c-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="7a35c-103">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="7a35c-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="7a35c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7a35c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7a35c-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="7a35c-105">\<comContracts></span></span>  
<span data-ttu-id="7a35c-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="7a35c-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a35c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a35c-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="7a35c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="7a35c-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a35c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a35c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7a35c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7a35c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a35c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a35c-111">Attributes</span></span>  
  
|<span data-ttu-id="7a35c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7a35c-112">Attribute</span></span>|<span data-ttu-id="7a35c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7a35c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a35c-114">id</span><span class="sxs-lookup"><span data-stu-id="7a35c-114">id</span></span>|<span data-ttu-id="7a35c-115">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="7a35c-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="7a35c-116">имя</span><span class="sxs-lookup"><span data-stu-id="7a35c-116">name</span></span>|<span data-ttu-id="7a35c-117">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="7a35c-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a35c-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a35c-118">Child Elements</span></span>  
 <span data-ttu-id="7a35c-119">Нет</span><span class="sxs-lookup"><span data-stu-id="7a35c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a35c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a35c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a35c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a35c-121">Element</span></span>|<span data-ttu-id="7a35c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7a35c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a35c-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="7a35c-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="7a35c-124">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="7a35c-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a35c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7a35c-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="7a35c-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="7a35c-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="7a35c-127">Интеграция с приложениями COM +</span><span class="sxs-lookup"><span data-stu-id="7a35c-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="7a35c-128">Как: Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="7a35c-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
