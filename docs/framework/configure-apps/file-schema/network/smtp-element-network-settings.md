---
title: '&lt;SMTP&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56912e09d24fc83e93a91cc42b1d96dcc68210f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="ce9ee-102">&lt;SMTP&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ce9ee-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ce9ee-103">Настраивает формат доставки инструкций, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="ce9ee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce9ee-104">\<configuration></span></span>  
<span data-ttu-id="ce9ee-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="ce9ee-105">\<system.net></span></span>  
<span data-ttu-id="ce9ee-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="ce9ee-106">\<mailSettings></span></span>  
<span data-ttu-id="ce9ee-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="ce9ee-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9ee-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce9ee-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce9ee-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce9ee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ce9ee-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce9ee-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce9ee-111">Attributes</span></span>  
  
|<span data-ttu-id="ce9ee-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ce9ee-112">Attribute</span></span>|<span data-ttu-id="ce9ee-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ce9ee-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="ce9ee-114">Указывает формат доставки для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="ce9ee-115">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="ce9ee-116">Указывает способ доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="ce9ee-117">Допустимые значения: сеть, pickupDirectoryFromIis и specifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="ce9ee-118">Указывает адрес отправителя для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce9ee-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce9ee-119">Child Elements</span></span>  
  
|<span data-ttu-id="ce9ee-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ce9ee-120">Attribute</span></span>|<span data-ttu-id="ce9ee-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ce9ee-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="ce9ee-122">Настраивает локальный каталог для сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="ce9ee-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="ce9ee-123">Настройка сетевых параметров для внешнего сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce9ee-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce9ee-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ce9ee-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ce9ee-125">**Element**</span></span>|<span data-ttu-id="ce9ee-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ce9ee-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce9ee-127">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ce9ee-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="ce9ee-128">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ce9ee-129">Пример</span><span class="sxs-lookup"><span data-stu-id="ce9ee-129">Example</span></span>  
 <span data-ttu-id="ce9ee-130">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ce9ee-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce9ee-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ce9ee-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="ce9ee-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ce9ee-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
