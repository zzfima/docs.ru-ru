---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855061"
---
# <a name="policyimporter"></a><span data-ttu-id="7ad19-101">\<Полициимпортер ></span><span class="sxs-lookup"><span data-stu-id="7ad19-101">\<policyImporter></span></span>
<span data-ttu-id="7ad19-102">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="7ad19-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="7ad19-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7ad19-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7ad19-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7ad19-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7ad19-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="7ad19-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7ad19-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> метаданных**](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="7ad19-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="7ad19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Полициимпортерс >** ](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="7ad19-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="7ad19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Полициимпортер >**</span><span class="sxs-lookup"><span data-stu-id="7ad19-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad19-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ad19-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ad19-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7ad19-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ad19-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7ad19-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ad19-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7ad19-112">Attributes</span></span>  
  
|<span data-ttu-id="7ad19-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7ad19-113">Attribute</span></span>|<span data-ttu-id="7ad19-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7ad19-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7ad19-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="7ad19-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ad19-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7ad19-116">Child Elements</span></span>  
 <span data-ttu-id="7ad19-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7ad19-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ad19-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7ad19-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7ad19-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="7ad19-119">Element</span></span>|<span data-ttu-id="7ad19-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7ad19-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ad19-121">\<Полициимпортерс ></span><span class="sxs-lookup"><span data-stu-id="7ad19-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="7ad19-122">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="7ad19-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ad19-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ad19-123">Remarks</span></span>  
 <span data-ttu-id="7ad19-124">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="7ad19-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad19-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7ad19-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="7ad19-126">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="7ad19-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7ad19-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="7ad19-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
