---
title: "&lt;SMTP&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f5b2a3b7eec17fbdd12181c29f610d2b2ad32bd4
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="2eab4-102">&lt;SMTP&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2eab4-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2eab4-103">Настраивает формат доставки инструкций, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2eab4-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="2eab4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2eab4-104">\<configuration></span></span>  
<span data-ttu-id="2eab4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2eab4-105">\<system.net></span></span>  
<span data-ttu-id="2eab4-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="2eab4-106">\<mailSettings></span></span>  
<span data-ttu-id="2eab4-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="2eab4-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eab4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eab4-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2eab4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2eab4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2eab4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2eab4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2eab4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2eab4-111">Attributes</span></span>  
  
|<span data-ttu-id="2eab4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2eab4-112">Attribute</span></span>|<span data-ttu-id="2eab4-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="2eab4-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="2eab4-114">Указывает формат доставки для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2eab4-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="2eab4-115">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="2eab4-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="2eab4-116">Указывает способ доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2eab4-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="2eab4-117">Допустимые значения: сеть, pickupDirectoryFromIis и specifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="2eab4-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="2eab4-118">Указывает адрес отправителя для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2eab4-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2eab4-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2eab4-119">Child Elements</span></span>  
  
|<span data-ttu-id="2eab4-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2eab4-120">Attribute</span></span>|<span data-ttu-id="2eab4-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="2eab4-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="2eab4-122">Настраивает локальный каталог для сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="2eab4-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="2eab4-123">Настройка сетевых параметров для внешнего сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="2eab4-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2eab4-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2eab4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2eab4-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2eab4-125">**Element**</span></span>|<span data-ttu-id="2eab4-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2eab4-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2eab4-127">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2eab4-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="2eab4-128">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="2eab4-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2eab4-129">Пример</span><span class="sxs-lookup"><span data-stu-id="2eab4-129">Example</span></span>  
 <span data-ttu-id="2eab4-130">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2eab4-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2eab4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2eab4-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="2eab4-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2eab4-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
