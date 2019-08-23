---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940613"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="d8b43-101">\<Усеманажедпресентатион ></span><span class="sxs-lookup"><span data-stu-id="d8b43-101">\<useManagedPresentation></span></span>
<span data-ttu-id="d8b43-102">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d8b43-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="d8b43-103">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="d8b43-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="d8b43-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="d8b43-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d8b43-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d8b43-105">\<bindings></span></span>  
<span data-ttu-id="d8b43-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d8b43-106">\<customBinding></span></span>  
<span data-ttu-id="d8b43-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d8b43-107">\<binding></span></span>  
<span data-ttu-id="d8b43-108">\<Усеманажедпресентатион ></span><span class="sxs-lookup"><span data-stu-id="d8b43-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b43-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8b43-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b43-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8b43-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8b43-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8b43-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b43-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8b43-112">Attributes</span></span>  
 <span data-ttu-id="d8b43-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="d8b43-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8b43-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8b43-114">Child Elements</span></span>  
 <span data-ttu-id="d8b43-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="d8b43-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b43-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8b43-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b43-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8b43-117">Element</span></span>|<span data-ttu-id="d8b43-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d8b43-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8b43-119">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d8b43-119">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="d8b43-120">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d8b43-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b43-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8b43-121">Remarks</span></span>  
 <span data-ttu-id="d8b43-122">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d8b43-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="d8b43-123">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="d8b43-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b43-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d8b43-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d8b43-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="d8b43-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d8b43-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d8b43-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d8b43-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d8b43-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d8b43-128">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d8b43-128">\<customBinding></span></span>](custombinding.md)
