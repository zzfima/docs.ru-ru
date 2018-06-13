---
title: '&lt;transport&gt; для &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 9116532c8b4aae2f7539706b97d564444195c79d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753148"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="4e761-102">&lt;transport&gt; для &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="4e761-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="4e761-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="4e761-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="4e761-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4e761-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e761-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4e761-105">\<bindings></span></span>  
<span data-ttu-id="4e761-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="4e761-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="4e761-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4e761-107">\<binding></span></span>  
<span data-ttu-id="4e761-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="4e761-108">\<security></span></span>  
<span data-ttu-id="4e761-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="4e761-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e761-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e761-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e761-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e761-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4e761-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4e761-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e761-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e761-113">Attributes</span></span>  
  
|<span data-ttu-id="4e761-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4e761-114">Attribute</span></span>|<span data-ttu-id="4e761-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4e761-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e761-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="4e761-116">protectionLevel</span></span>|<span data-ttu-id="4e761-117">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="4e761-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="4e761-118">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="4e761-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="4e761-119">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="4e761-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="4e761-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4e761-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4e761-121">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="4e761-121">-   None: No protection.</span></span><br /><span data-ttu-id="4e761-122">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="4e761-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="4e761-123">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="4e761-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="4e761-124">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="4e761-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e761-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e761-125">Child Elements</span></span>  
 <span data-ttu-id="4e761-126">Нет</span><span class="sxs-lookup"><span data-stu-id="4e761-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e761-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e761-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4e761-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e761-128">Element</span></span>|<span data-ttu-id="4e761-129">Описание</span><span class="sxs-lookup"><span data-stu-id="4e761-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e761-130">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="4e761-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="4e761-131">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="4e761-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e761-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4e761-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="4e761-133">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4e761-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4e761-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="4e761-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4e761-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4e761-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4e761-136">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="4e761-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4e761-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4e761-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
