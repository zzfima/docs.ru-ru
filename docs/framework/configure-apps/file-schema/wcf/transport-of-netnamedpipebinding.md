---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 6ea0b1e374659bbbbb2f47630c009f823ccd4de9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399331"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="7b14b-102">\<транспортное \<> из NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="7b14b-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="7b14b-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="7b14b-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="7b14b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b14b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b14b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7b14b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7b14b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7b14b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7b14b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b14b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="7b14b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="7b14b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7b14b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b14b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="7b14b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> транспорта**</span><span class="sxs-lookup"><span data-stu-id="7b14b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b14b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b14b-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b14b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b14b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7b14b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b14b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b14b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b14b-114">Attributes</span></span>  
  
|<span data-ttu-id="7b14b-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b14b-115">Attribute</span></span>|<span data-ttu-id="7b14b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7b14b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b14b-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7b14b-117">protectionLevel</span></span>|<span data-ttu-id="7b14b-118">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="7b14b-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="7b14b-119">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="7b14b-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7b14b-120">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="7b14b-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="7b14b-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7b14b-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7b14b-122">None Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="7b14b-122">-   None: No protection.</span></span><br /><span data-ttu-id="7b14b-123">Писать Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="7b14b-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="7b14b-124">EncryptAndSign Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="7b14b-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="7b14b-125">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="7b14b-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b14b-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b14b-126">Child Elements</span></span>  
 <span data-ttu-id="7b14b-127">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="7b14b-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b14b-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b14b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7b14b-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b14b-129">Element</span></span>|<span data-ttu-id="7b14b-130">Описание</span><span class="sxs-lookup"><span data-stu-id="7b14b-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b14b-131">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="7b14b-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="7b14b-132">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="7b14b-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b14b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7b14b-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="7b14b-134">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7b14b-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7b14b-135">Привязки</span><span class="sxs-lookup"><span data-stu-id="7b14b-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7b14b-136">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7b14b-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7b14b-137">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7b14b-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7b14b-138">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7b14b-138">\<binding></span></span>](../../../misc/binding.md)
