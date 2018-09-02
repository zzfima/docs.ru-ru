---
title: '&lt;transport&gt; для &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 0006be71ee67d5f274d8af8087f2d111cddb12b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407259"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="1e00b-102">&lt;transport&gt; для &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1e00b-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="1e00b-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="1e00b-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="1e00b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1e00b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e00b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1e00b-105">\<bindings></span></span>  
<span data-ttu-id="1e00b-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="1e00b-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="1e00b-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1e00b-107">\<binding></span></span>  
<span data-ttu-id="1e00b-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="1e00b-108">\<security></span></span>  
<span data-ttu-id="1e00b-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="1e00b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e00b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e00b-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e00b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e00b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1e00b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e00b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e00b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e00b-113">Attributes</span></span>  
  
|<span data-ttu-id="1e00b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e00b-114">Attribute</span></span>|<span data-ttu-id="1e00b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1e00b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e00b-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="1e00b-116">protectionLevel</span></span>|<span data-ttu-id="1e00b-117">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="1e00b-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="1e00b-118">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="1e00b-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1e00b-119">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="1e00b-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="1e00b-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1e00b-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1e00b-121">-None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="1e00b-121">-   None: No protection.</span></span><br /><span data-ttu-id="1e00b-122">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="1e00b-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1e00b-123">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="1e00b-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1e00b-124">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="1e00b-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e00b-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e00b-125">Child Elements</span></span>  
 <span data-ttu-id="1e00b-126">Нет</span><span class="sxs-lookup"><span data-stu-id="1e00b-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e00b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e00b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1e00b-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e00b-128">Element</span></span>|<span data-ttu-id="1e00b-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e00b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e00b-130">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="1e00b-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="1e00b-131">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="1e00b-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e00b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1e00b-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="1e00b-133">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1e00b-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1e00b-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="1e00b-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1e00b-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="1e00b-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1e00b-136">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="1e00b-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1e00b-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1e00b-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
