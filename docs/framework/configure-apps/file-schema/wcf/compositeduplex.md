---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: f8615637a0fa6d0fff594ef1970711ac408f02f3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264509"
---
# <a name="compositeduplex"></a><span data-ttu-id="92912-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="92912-101">\<compositeDuplex></span></span>
<span data-ttu-id="92912-102">Определяет элемент привязки, который используется, когда клиенту необходимо предоставить службе конечную точку для отправки сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="92912-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="92912-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="92912-103">\<system.serviceModel></span></span>  
<span data-ttu-id="92912-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="92912-104">\<bindings></span></span>  
<span data-ttu-id="92912-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="92912-105">\<customBinding></span></span>  
<span data-ttu-id="92912-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="92912-106">\<binding></span></span>  
<span data-ttu-id="92912-107">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="92912-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92912-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92912-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92912-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92912-109">Attributes and Elements</span></span>  
 <span data-ttu-id="92912-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92912-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92912-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92912-111">Attributes</span></span>  
  
|<span data-ttu-id="92912-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="92912-112">Attribute</span></span>|<span data-ttu-id="92912-113">Описание</span><span class="sxs-lookup"><span data-stu-id="92912-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92912-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="92912-114">clientBaseAddress</span></span>|<span data-ttu-id="92912-115">Универсальный код ресурса (URI), который задает адрес обратного канала при работе в дуплексном режиме.</span><span class="sxs-lookup"><span data-stu-id="92912-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="92912-116">Служба использует данный адрес для осуществления контакта и создания подключения к клиенту.</span><span class="sxs-lookup"><span data-stu-id="92912-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="92912-117">Если этот атрибут не установлен, адрес по умолчанию "`full qualified name+default port\TemporaryIndigoAddress\guid`" создается.</span><span class="sxs-lookup"><span data-stu-id="92912-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="92912-118">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="92912-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92912-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92912-119">Child Elements</span></span>  
 <span data-ttu-id="92912-120">Нет</span><span class="sxs-lookup"><span data-stu-id="92912-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92912-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92912-121">Parent Elements</span></span>  
  
|<span data-ttu-id="92912-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="92912-122">Element</span></span>|<span data-ttu-id="92912-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="92912-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92912-124">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="92912-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="92912-125">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="92912-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92912-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="92912-126">Remarks</span></span>  
 <span data-ttu-id="92912-127">Данный элемент конфигурации используется с теми типами транспорта, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="92912-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="92912-128">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="92912-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="92912-129">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="92912-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="92912-130">Этот адрес клиента предоставляется атрибутом `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="92912-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="92912-131">Обратите внимание, что Windows Communication Foundation (WCF) автоматически создает атрибут ClientBaseAddress в том случае, если он не был явно задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="92912-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92912-132">Пример</span><span class="sxs-lookup"><span data-stu-id="92912-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="92912-133">См. также</span><span class="sxs-lookup"><span data-stu-id="92912-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="92912-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="92912-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="92912-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="92912-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="92912-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="92912-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="92912-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="92912-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
