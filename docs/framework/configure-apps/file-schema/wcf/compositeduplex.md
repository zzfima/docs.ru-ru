---
title: '&lt;compositeDuplex&gt;'
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: ce04eb96868da9760412e37d2335d020cc768ac9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="41e47-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="41e47-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="41e47-103">Определяет элемент привязки, который используется, когда клиенту необходимо предоставить службе конечную точку для отправки сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="41e47-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="41e47-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="41e47-104">\<system.serviceModel></span></span>  
<span data-ttu-id="41e47-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="41e47-105">\<bindings></span></span>  
<span data-ttu-id="41e47-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="41e47-106">\<customBinding></span></span>  
<span data-ttu-id="41e47-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="41e47-107">\<binding></span></span>  
<span data-ttu-id="41e47-108">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="41e47-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e47-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41e47-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41e47-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41e47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="41e47-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="41e47-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41e47-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41e47-112">Attributes</span></span>  
  
|<span data-ttu-id="41e47-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="41e47-113">Attribute</span></span>|<span data-ttu-id="41e47-114">Описание</span><span class="sxs-lookup"><span data-stu-id="41e47-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41e47-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="41e47-115">clientBaseAddress</span></span>|<span data-ttu-id="41e47-116">Универсальный код ресурса (URI), который задает адрес обратного канала при работе в дуплексном режиме.</span><span class="sxs-lookup"><span data-stu-id="41e47-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="41e47-117">Служба использует данный адрес для осуществления контакта и создания подключения к клиенту.</span><span class="sxs-lookup"><span data-stu-id="41e47-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="41e47-118">Если этот атрибут не установлен, адрес по умолчанию «`full qualified name+default port\TemporaryIndigoAddress\guid`» создается.</span><span class="sxs-lookup"><span data-stu-id="41e47-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="41e47-119">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="41e47-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41e47-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41e47-120">Child Elements</span></span>  
 <span data-ttu-id="41e47-121">Нет</span><span class="sxs-lookup"><span data-stu-id="41e47-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41e47-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41e47-122">Parent Elements</span></span>  
  
|<span data-ttu-id="41e47-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="41e47-123">Element</span></span>|<span data-ttu-id="41e47-124">Описание</span><span class="sxs-lookup"><span data-stu-id="41e47-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41e47-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="41e47-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="41e47-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="41e47-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41e47-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="41e47-127">Remarks</span></span>  
 <span data-ttu-id="41e47-128">Данный элемент конфигурации используется с теми типами транспорта, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="41e47-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="41e47-129">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="41e47-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="41e47-130">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="41e47-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="41e47-131">Этот адрес клиента предоставляется атрибутом `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="41e47-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="41e47-132">Обратите внимание, что Windows Communication Foundation (WCF) автоматически создает атрибут ClientBaseAddress в том случае, если он не был явно задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="41e47-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e47-133">Пример</span><span class="sxs-lookup"><span data-stu-id="41e47-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="41e47-134">См. также</span><span class="sxs-lookup"><span data-stu-id="41e47-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>  
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="41e47-135">Привязки</span><span class="sxs-lookup"><span data-stu-id="41e47-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="41e47-136">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="41e47-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="41e47-137">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="41e47-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="41e47-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="41e47-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
