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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c77bdf8ef02edf682ded95ab16b4d56dbf60b4ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="53e23-102">&lt;Восстанавливаемый тип persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="53e23-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="53e23-103">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="53e23-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="53e23-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="53e23-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53e23-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="53e23-105">\<comContracts></span></span>  
<span data-ttu-id="53e23-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="53e23-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e23-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53e23-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="53e23-108">Тип</span><span class="sxs-lookup"><span data-stu-id="53e23-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53e23-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53e23-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53e23-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53e23-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53e23-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53e23-111">Attributes</span></span>  
  
|<span data-ttu-id="53e23-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="53e23-112">Attribute</span></span>|<span data-ttu-id="53e23-113">Описание</span><span class="sxs-lookup"><span data-stu-id="53e23-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53e23-114">id</span><span class="sxs-lookup"><span data-stu-id="53e23-114">id</span></span>|<span data-ttu-id="53e23-115">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="53e23-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="53e23-116">имя</span><span class="sxs-lookup"><span data-stu-id="53e23-116">name</span></span>|<span data-ttu-id="53e23-117">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="53e23-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53e23-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53e23-118">Child Elements</span></span>  
 <span data-ttu-id="53e23-119">Нет</span><span class="sxs-lookup"><span data-stu-id="53e23-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53e23-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53e23-120">Parent Elements</span></span>  
  
|<span data-ttu-id="53e23-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="53e23-121">Element</span></span>|<span data-ttu-id="53e23-122">Описание</span><span class="sxs-lookup"><span data-stu-id="53e23-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53e23-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="53e23-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="53e23-124">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="53e23-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53e23-125">См. также</span><span class="sxs-lookup"><span data-stu-id="53e23-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="53e23-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="53e23-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="53e23-127">Интеграция с приложениями COM +</span><span class="sxs-lookup"><span data-stu-id="53e23-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="53e23-128">Как: Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="53e23-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
