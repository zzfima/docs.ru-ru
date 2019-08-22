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
ms.openlocfilehash: ac9405fdc6123a5a1352de06f94fefb6d7d4014b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659123"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="2fba6-102">\<Элемент > SMTP (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2fba6-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="2fba6-103">Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2fba6-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="2fba6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2fba6-104">\<configuration></span></span>  
<span data-ttu-id="2fba6-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="2fba6-105">\<system.net></span></span>  
<span data-ttu-id="2fba6-106">\<Маилсеттингс ></span><span class="sxs-lookup"><span data-stu-id="2fba6-106">\<mailSettings></span></span>  
<span data-ttu-id="2fba6-107">\<> SMTP</span><span class="sxs-lookup"><span data-stu-id="2fba6-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fba6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fba6-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fba6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fba6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2fba6-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2fba6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fba6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fba6-111">Attributes</span></span>  
  
|<span data-ttu-id="2fba6-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2fba6-112">Attribute</span></span>|<span data-ttu-id="2fba6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2fba6-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="2fba6-114">Указывает формат доставки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2fba6-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="2fba6-115">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="2fba6-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="2fba6-116">Указывает метод доставки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2fba6-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="2fba6-117">Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.</span><span class="sxs-lookup"><span data-stu-id="2fba6-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="2fba6-118">Указывает адрес отсылаемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2fba6-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2fba6-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fba6-119">Child Elements</span></span>  
  
|<span data-ttu-id="2fba6-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2fba6-120">Attribute</span></span>|<span data-ttu-id="2fba6-121">Описание</span><span class="sxs-lookup"><span data-stu-id="2fba6-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="2fba6-122">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="2fba6-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="2fba6-123">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="2fba6-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fba6-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fba6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2fba6-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2fba6-125">**Element**</span></span>|<span data-ttu-id="2fba6-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2fba6-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2fba6-127">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2fba6-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="2fba6-128">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="2fba6-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2fba6-129">Пример</span><span class="sxs-lookup"><span data-stu-id="2fba6-129">Example</span></span>  
 <span data-ttu-id="2fba6-130">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2fba6-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2fba6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2fba6-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="2fba6-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2fba6-132">Network Settings Schema</span></span>](index.md)
