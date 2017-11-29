---
title: '&lt;compositeDuplex&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9f82d4b6ac69e0edc0a2ad2cddfd89ee6ac72db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="ce804-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="ce804-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="ce804-103">Определяет элемент привязки, который используется, когда клиенту необходимо предоставить службе конечную точку для отправки сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="ce804-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="ce804-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ce804-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ce804-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ce804-105">\<bindings></span></span>  
<span data-ttu-id="ce804-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ce804-106">\<customBinding></span></span>  
<span data-ttu-id="ce804-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ce804-107">\<binding></span></span>  
<span data-ttu-id="ce804-108">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="ce804-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce804-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce804-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce804-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce804-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce804-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce804-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce804-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce804-112">Attributes</span></span>  
  
|<span data-ttu-id="ce804-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ce804-113">Attribute</span></span>|<span data-ttu-id="ce804-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ce804-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce804-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="ce804-115">clientBaseAddress</span></span>|<span data-ttu-id="ce804-116">Универсальный код ресурса (URI), который задает адрес обратного канала при работе в дуплексном режиме.</span><span class="sxs-lookup"><span data-stu-id="ce804-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="ce804-117">Служба использует данный адрес для осуществления контакта и создания подключения к клиенту.</span><span class="sxs-lookup"><span data-stu-id="ce804-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="ce804-118">Если этот атрибут не установлен, адрес по умолчанию «`full qualified name+default port\TemporaryIndigoAddress\guid`» создается.</span><span class="sxs-lookup"><span data-stu-id="ce804-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="ce804-119">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="ce804-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce804-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce804-120">Child Elements</span></span>  
 <span data-ttu-id="ce804-121">Нет</span><span class="sxs-lookup"><span data-stu-id="ce804-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce804-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce804-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ce804-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce804-123">Element</span></span>|<span data-ttu-id="ce804-124">Описание</span><span class="sxs-lookup"><span data-stu-id="ce804-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce804-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ce804-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ce804-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ce804-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce804-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce804-127">Remarks</span></span>  
 <span data-ttu-id="ce804-128">Данный элемент конфигурации используется с теми типами транспорта, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="ce804-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="ce804-129">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="ce804-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="ce804-130">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="ce804-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="ce804-131">Этот адрес клиента предоставляется атрибутом `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="ce804-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="ce804-132">Обратите внимание, что Windows Communication Foundation (WCF) автоматически создает атрибут ClientBaseAddress в том случае, если он не был явно задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="ce804-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce804-133">Пример</span><span class="sxs-lookup"><span data-stu-id="ce804-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce804-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ce804-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>  
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ce804-135">Привязки</span><span class="sxs-lookup"><span data-stu-id="ce804-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ce804-136">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ce804-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="ce804-137">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="ce804-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="ce804-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ce804-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
