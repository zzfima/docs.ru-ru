---
title: '&lt;useManagedPresentation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3aeb64513401164c9c5acb24ede48c2e9aa2b4b3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="2d996-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="2d996-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="2d996-103">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="2d996-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="2d996-104">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="2d996-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="2d996-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2d996-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2d996-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="2d996-106">\<bindings></span></span>  
<span data-ttu-id="2d996-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2d996-107">\<customBinding></span></span>  
<span data-ttu-id="2d996-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2d996-108">\<binding></span></span>  
<span data-ttu-id="2d996-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="2d996-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d996-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d996-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d996-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2d996-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2d996-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2d996-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d996-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2d996-113">Attributes</span></span>  
 <span data-ttu-id="2d996-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2d996-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d996-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2d996-115">Child Elements</span></span>  
 <span data-ttu-id="2d996-116">Нет</span><span class="sxs-lookup"><span data-stu-id="2d996-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d996-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2d996-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2d996-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d996-118">Element</span></span>|<span data-ttu-id="2d996-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2d996-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d996-120">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2d996-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2d996-121">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="2d996-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d996-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d996-122">Remarks</span></span>  
 <span data-ttu-id="2d996-123">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="2d996-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="2d996-124">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="2d996-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d996-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2d996-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="2d996-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="2d996-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2d996-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="2d996-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="2d996-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="2d996-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="2d996-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2d996-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
