---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735957"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="cfe17-102">\<> транспорта \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="cfe17-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="cfe17-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cfe17-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="cfe17-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfe17-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfe17-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cfe17-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cfe17-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="cfe17-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="cfe17-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfe17-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="cfe17-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="cfe17-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cfe17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfe17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="cfe17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**транспорта >**</span><span class="sxs-lookup"><span data-stu-id="cfe17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfe17-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfe17-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfe17-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cfe17-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cfe17-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cfe17-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfe17-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cfe17-114">Attributes</span></span>  
  
|<span data-ttu-id="cfe17-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cfe17-115">Attribute</span></span>|<span data-ttu-id="cfe17-116">Описание</span><span class="sxs-lookup"><span data-stu-id="cfe17-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfe17-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="cfe17-117">protectionLevel</span></span>|<span data-ttu-id="cfe17-118">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cfe17-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="cfe17-119">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="cfe17-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="cfe17-120">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="cfe17-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="cfe17-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="cfe17-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cfe17-122">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cfe17-122">-   None: No protection.</span></span><br /><span data-ttu-id="cfe17-123">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="cfe17-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="cfe17-124">-EncryptAndSign: сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="cfe17-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="cfe17-125">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="cfe17-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfe17-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cfe17-126">Child Elements</span></span>  
 <span data-ttu-id="cfe17-127">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="cfe17-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfe17-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cfe17-128">Parent Elements</span></span>  
  
|<span data-ttu-id="cfe17-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="cfe17-129">Element</span></span>|<span data-ttu-id="cfe17-130">Описание</span><span class="sxs-lookup"><span data-stu-id="cfe17-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfe17-131">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="cfe17-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="cfe17-132">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="cfe17-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfe17-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cfe17-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="cfe17-134">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cfe17-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cfe17-135">Привязки</span><span class="sxs-lookup"><span data-stu-id="cfe17-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cfe17-136">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cfe17-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cfe17-137">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cfe17-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cfe17-138">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="cfe17-138">\<binding></span></span>](bindings.md)
