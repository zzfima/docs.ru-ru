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
ms.openlocfilehash: 1b5f7406f995a86f0a192dbf3249c067dff570ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140378"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="bb712-102">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="bb712-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="bb712-103">Настраивает формат и способ доставки и адрес отправителя для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb712-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="bb712-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb712-104">\<configuration></span></span>  
<span data-ttu-id="bb712-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="bb712-105">\<system.net></span></span>  
<span data-ttu-id="bb712-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="bb712-106">\<mailSettings></span></span>  
<span data-ttu-id="bb712-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="bb712-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb712-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb712-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb712-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb712-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bb712-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb712-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb712-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb712-111">Attributes</span></span>  
  
|<span data-ttu-id="bb712-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb712-112">Attribute</span></span>|<span data-ttu-id="bb712-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bb712-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="bb712-114">Задает формат доставки для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb712-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="bb712-115">Допустимые значения: SevenBit и International.</span><span class="sxs-lookup"><span data-stu-id="bb712-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="bb712-116">Задает метод доставки для сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb712-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="bb712-117">Допустимые значения: сети, PickupDirectoryFromIis и SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="bb712-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="bb712-118">Указывает адрес отправителя для исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bb712-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb712-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb712-119">Child Elements</span></span>  
  
|<span data-ttu-id="bb712-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb712-120">Attribute</span></span>|<span data-ttu-id="bb712-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bb712-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="bb712-122">Настраивает локальный каталог для сервера транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="bb712-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="bb712-123">Настройка сетевых параметров для внешнего сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="bb712-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb712-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb712-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bb712-125">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="bb712-125">**Element**</span></span>|<span data-ttu-id="bb712-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bb712-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bb712-127">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bb712-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="bb712-128">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="bb712-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bb712-129">Пример</span><span class="sxs-lookup"><span data-stu-id="bb712-129">Example</span></span>  
 <span data-ttu-id="bb712-130">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb712-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb712-131">См. также</span><span class="sxs-lookup"><span data-stu-id="bb712-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="bb712-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="bb712-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
