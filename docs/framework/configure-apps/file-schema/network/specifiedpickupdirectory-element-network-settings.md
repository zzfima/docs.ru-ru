---
title: '&lt;specifiedPickupDirectory&gt; (сетевые параметры)'
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
ms.openlocfilehash: b62dc1a9118f7d4f1f693ade36626deaecd23999
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863654"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="878d1-102">&lt;specifiedPickupDirectory&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="878d1-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="878d1-103">Настраивает локальный каталог для сервера транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="878d1-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="878d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="878d1-104">\<configuration></span></span>  
<span data-ttu-id="878d1-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="878d1-105">\<system.net></span></span>  
<span data-ttu-id="878d1-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="878d1-106">\<mailSettings></span></span>  
<span data-ttu-id="878d1-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="878d1-107">\<smtp></span></span>  
<span data-ttu-id="878d1-108">\<specifiedPickupDirectory ></span><span class="sxs-lookup"><span data-stu-id="878d1-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878d1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="878d1-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="878d1-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="878d1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="878d1-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="878d1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="878d1-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="878d1-112">Attributes</span></span>  
  
|<span data-ttu-id="878d1-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="878d1-113">Attribute</span></span>|<span data-ttu-id="878d1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="878d1-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="878d1-115">Каталог, в которой приложения сохраняют сообщения электронной почты для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="878d1-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="878d1-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="878d1-116">Child Elements</span></span>  
 <span data-ttu-id="878d1-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="878d1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="878d1-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="878d1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="878d1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="878d1-119">Element</span></span>|<span data-ttu-id="878d1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="878d1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="878d1-121">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="878d1-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="878d1-122">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="878d1-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="878d1-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="878d1-123">Remarks</span></span>  
 <span data-ttu-id="878d1-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="878d1-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="878d1-125">Пример</span><span class="sxs-lookup"><span data-stu-id="878d1-125">Example</span></span>  
 <span data-ttu-id="878d1-126">Следующий пример определяет c:\maildrop как каталог раскладки почты.</span><span class="sxs-lookup"><span data-stu-id="878d1-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="878d1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="878d1-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="878d1-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="878d1-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
