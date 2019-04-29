---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a6d3dd2c24e90bdcdc6520e62dcc1dbe7ce797f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788353"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="5cddb-102">\<Транспорт > из \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="5cddb-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="5cddb-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="5cddb-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="5cddb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5cddb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cddb-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="5cddb-105">\<bindings></span></span>  
<span data-ttu-id="5cddb-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="5cddb-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="5cddb-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5cddb-107">\<binding></span></span>  
<span data-ttu-id="5cddb-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="5cddb-108">\<security></span></span>  
<span data-ttu-id="5cddb-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="5cddb-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cddb-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cddb-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cddb-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5cddb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5cddb-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5cddb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cddb-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cddb-113">Attributes</span></span>  
  
|<span data-ttu-id="5cddb-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5cddb-114">Attribute</span></span>|<span data-ttu-id="5cddb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5cddb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cddb-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5cddb-116">protectionLevel</span></span>|<span data-ttu-id="5cddb-117">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="5cddb-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="5cddb-118">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="5cddb-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5cddb-119">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="5cddb-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="5cddb-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5cddb-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5cddb-121">-None: Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="5cddb-121">-   None: No protection.</span></span><br /><span data-ttu-id="5cddb-122">-Входа: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="5cddb-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5cddb-123">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="5cddb-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="5cddb-124">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="5cddb-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cddb-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5cddb-125">Child Elements</span></span>  
 <span data-ttu-id="5cddb-126">Нет</span><span class="sxs-lookup"><span data-stu-id="5cddb-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cddb-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5cddb-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5cddb-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cddb-128">Element</span></span>|<span data-ttu-id="5cddb-129">Описание</span><span class="sxs-lookup"><span data-stu-id="5cddb-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cddb-130">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="5cddb-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="5cddb-131">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="5cddb-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cddb-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5cddb-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="5cddb-133">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5cddb-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5cddb-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="5cddb-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5cddb-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5cddb-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5cddb-136">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5cddb-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5cddb-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5cddb-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
