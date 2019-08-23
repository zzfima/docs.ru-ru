---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 1e76d0962ea7b4714ef6ca1f9d4c4c3e23df5b6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934676"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="e2b3f-102">\<транспортное \<> из NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e2b3f-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="e2b3f-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="e2b3f-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2b3f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2b3f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e2b3f-105">\<bindings></span></span>  
<span data-ttu-id="e2b3f-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e2b3f-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e2b3f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e2b3f-107">\<binding></span></span>  
<span data-ttu-id="e2b3f-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="e2b3f-108">\<security></span></span>  
<span data-ttu-id="e2b3f-109">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="e2b3f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b3f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2b3f-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2b3f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2b3f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e2b3f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2b3f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2b3f-113">Attributes</span></span>  
  
|<span data-ttu-id="e2b3f-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2b3f-114">Attribute</span></span>|<span data-ttu-id="e2b3f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e2b3f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2b3f-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e2b3f-116">protectionLevel</span></span>|<span data-ttu-id="e2b3f-117">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e2b3f-118">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e2b3f-119">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e2b3f-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e2b3f-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2b3f-121">None Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-121">-   None: No protection.</span></span><br /><span data-ttu-id="e2b3f-122">Писать Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e2b3f-123">EncryptAndSign Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e2b3f-124">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2b3f-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2b3f-125">Child Elements</span></span>  
 <span data-ttu-id="e2b3f-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e2b3f-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2b3f-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2b3f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e2b3f-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2b3f-128">Element</span></span>|<span data-ttu-id="e2b3f-129">Описание</span><span class="sxs-lookup"><span data-stu-id="e2b3f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b3f-130">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="e2b3f-130">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="e2b3f-131">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="e2b3f-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2b3f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b3f-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="e2b3f-133">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e2b3f-133">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e2b3f-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="e2b3f-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2b3f-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e2b3f-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e2b3f-136">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e2b3f-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e2b3f-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e2b3f-137">\<binding></span></span>](../../../misc/binding.md)
