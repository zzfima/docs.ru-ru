---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 1134c4d5f18f60bb2986f4239a788b836fa9113e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287252"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="fdf6c-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="fdf6c-101">\<useManagedPresentation></span></span>
<span data-ttu-id="fdf6c-102">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="fdf6c-103">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="fdf6c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fdf6c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fdf6c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-105">\<bindings></span></span>  
<span data-ttu-id="fdf6c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-106">\<customBinding></span></span>  
<span data-ttu-id="fdf6c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-107">\<binding></span></span>  
<span data-ttu-id="fdf6c-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="fdf6c-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf6c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdf6c-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdf6c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fdf6c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fdf6c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdf6c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fdf6c-112">Attributes</span></span>  
 <span data-ttu-id="fdf6c-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fdf6c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fdf6c-114">Child Elements</span></span>  
 <span data-ttu-id="fdf6c-115">Нет</span><span class="sxs-lookup"><span data-stu-id="fdf6c-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdf6c-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fdf6c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fdf6c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="fdf6c-117">Element</span></span>|<span data-ttu-id="fdf6c-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="fdf6c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdf6c-119">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fdf6c-120">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdf6c-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="fdf6c-121">Remarks</span></span>  
 <span data-ttu-id="fdf6c-122">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="fdf6c-123">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="fdf6c-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf6c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fdf6c-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fdf6c-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="fdf6c-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fdf6c-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="fdf6c-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fdf6c-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="fdf6c-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fdf6c-128">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="fdf6c-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
