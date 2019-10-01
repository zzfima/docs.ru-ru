---
title: Элемент <smtp> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697612"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="8b494-102">Элемент > @no__t 0smtp (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8b494-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="8b494-103">Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8b494-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="8b494-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="8b494-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8b494-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8b494-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="8b494-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8b494-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="8b494-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="8b494-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b494-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b494-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b494-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8b494-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8b494-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8b494-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b494-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b494-111">Attributes</span></span>  
  
|<span data-ttu-id="8b494-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b494-112">Attribute</span></span>|<span data-ttu-id="8b494-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8b494-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="8b494-114">Указывает формат доставки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8b494-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="8b494-115">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="8b494-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="8b494-116">Указывает метод доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8b494-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="8b494-117">Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.</span><span class="sxs-lookup"><span data-stu-id="8b494-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="8b494-118">Указывает адрес отсылаемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8b494-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b494-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b494-119">Child Elements</span></span>  
  
|<span data-ttu-id="8b494-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b494-120">Attribute</span></span>|<span data-ttu-id="8b494-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8b494-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="8b494-122">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="8b494-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="8b494-123">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="8b494-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b494-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8b494-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8b494-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8b494-125">**Element**</span></span>|<span data-ttu-id="8b494-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8b494-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8b494-127">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8b494-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="8b494-128">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="8b494-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8b494-129">Пример</span><span class="sxs-lookup"><span data-stu-id="8b494-129">Example</span></span>  
 <span data-ttu-id="8b494-130">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b494-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="8b494-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8b494-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="8b494-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8b494-132">Network Settings Schema</span></span>](index.md)
