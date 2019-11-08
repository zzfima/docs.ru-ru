---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735944"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="e5935-101">\<Усеманажедпресентатион ></span><span class="sxs-lookup"><span data-stu-id="e5935-101">\<useManagedPresentation></span></span>
<span data-ttu-id="e5935-102">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="e5935-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="e5935-103">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="e5935-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="e5935-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5935-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5935-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5935-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5935-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="e5935-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="e5935-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e5935-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e5935-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="e5935-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e5935-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<усеманажедпресентатион >**</span><span class="sxs-lookup"><span data-stu-id="e5935-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5935-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5935-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5935-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5935-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5935-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5935-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5935-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5935-113">Attributes</span></span>  
 <span data-ttu-id="e5935-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e5935-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5935-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5935-115">Child Elements</span></span>  
 <span data-ttu-id="e5935-116">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e5935-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5935-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5935-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e5935-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5935-118">Element</span></span>|<span data-ttu-id="e5935-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e5935-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5935-120">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="e5935-120">\<binding></span></span>](bindings.md)|<span data-ttu-id="e5935-121">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e5935-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5935-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5935-122">Remarks</span></span>  
 <span data-ttu-id="e5935-123">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="e5935-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="e5935-124">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="e5935-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5935-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e5935-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e5935-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="e5935-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e5935-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e5935-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e5935-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e5935-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e5935-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e5935-129">\<customBinding></span></span>](custombinding.md)
