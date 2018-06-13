---
title: '&lt;specifiedPickupDirectory&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3a982bdbe4953691d4e8e7663f14059ff4771934
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743980"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="63e28-102">&lt;specifiedPickupDirectory&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="63e28-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="63e28-103">Настраивает локальный каталог для сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="63e28-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="63e28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="63e28-104">\<configuration></span></span>  
<span data-ttu-id="63e28-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="63e28-105">\<system.net></span></span>  
<span data-ttu-id="63e28-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="63e28-106">\<mailSettings></span></span>  
<span data-ttu-id="63e28-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="63e28-107">\<smtp></span></span>  
<span data-ttu-id="63e28-108">\<specifiedPickupDirectory ></span><span class="sxs-lookup"><span data-stu-id="63e28-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e28-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63e28-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63e28-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="63e28-110">Attributes and Elements</span></span>  
 <span data-ttu-id="63e28-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="63e28-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63e28-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="63e28-112">Attributes</span></span>  
  
|<span data-ttu-id="63e28-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="63e28-113">Attribute</span></span>|<span data-ttu-id="63e28-114">Описание</span><span class="sxs-lookup"><span data-stu-id="63e28-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="63e28-115">Каталог, где приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="63e28-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63e28-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="63e28-116">Child Elements</span></span>  
 <span data-ttu-id="63e28-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="63e28-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63e28-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="63e28-118">Parent Elements</span></span>  
  
|<span data-ttu-id="63e28-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="63e28-119">Element</span></span>|<span data-ttu-id="63e28-120">Описание</span><span class="sxs-lookup"><span data-stu-id="63e28-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63e28-121">\<SMTP > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="63e28-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="63e28-122">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="63e28-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e28-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="63e28-123">Remarks</span></span>  
 <span data-ttu-id="63e28-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="63e28-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e28-125">Пример</span><span class="sxs-lookup"><span data-stu-id="63e28-125">Example</span></span>  
 <span data-ttu-id="63e28-126">Следующий пример определяет c:\maildrop как каталог раскладки почты.</span><span class="sxs-lookup"><span data-stu-id="63e28-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63e28-127">См. также</span><span class="sxs-lookup"><span data-stu-id="63e28-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="63e28-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="63e28-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
