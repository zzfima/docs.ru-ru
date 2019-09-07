---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: c410967e84c9318d21ce0b3072d08b026a37b190
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399209"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="33378-101">\<Усеманажедпресентатион ></span><span class="sxs-lookup"><span data-stu-id="33378-101">\<useManagedPresentation></span></span>
<span data-ttu-id="33378-102">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="33378-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="33378-103">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="33378-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="33378-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33378-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33378-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33378-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33378-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="33378-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="33378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="33378-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="33378-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="33378-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="33378-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Усеманажедпресентатион >**</span><span class="sxs-lookup"><span data-stu-id="33378-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33378-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33378-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33378-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33378-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33378-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33378-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33378-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33378-113">Attributes</span></span>  
 <span data-ttu-id="33378-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="33378-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33378-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33378-115">Child Elements</span></span>  
 <span data-ttu-id="33378-116">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="33378-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33378-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33378-117">Parent Elements</span></span>  
  
|<span data-ttu-id="33378-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="33378-118">Element</span></span>|<span data-ttu-id="33378-119">Описание</span><span class="sxs-lookup"><span data-stu-id="33378-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33378-120">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="33378-120">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="33378-121">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="33378-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33378-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="33378-122">Remarks</span></span>  
 <span data-ttu-id="33378-123">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="33378-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="33378-124">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="33378-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33378-125">См. также</span><span class="sxs-lookup"><span data-stu-id="33378-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="33378-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="33378-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="33378-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="33378-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="33378-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="33378-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="33378-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="33378-129">\<customBinding></span></span>](custombinding.md)
