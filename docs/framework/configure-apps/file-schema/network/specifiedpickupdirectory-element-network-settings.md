---
title: "&lt;specifiedPickupDirectory&gt; элемент (параметры сети)"
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
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e68ce8cac4048ee2df89d0241cc50242e20391a2
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="85766-102">&lt;specifiedPickupDirectory&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="85766-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="85766-103">Настраивает локальный каталог для сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="85766-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="85766-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="85766-104">\<configuration></span></span>  
<span data-ttu-id="85766-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="85766-105">\<system.net></span></span>  
<span data-ttu-id="85766-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="85766-106">\<mailSettings></span></span>  
<span data-ttu-id="85766-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="85766-107">\<smtp></span></span>  
<span data-ttu-id="85766-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="85766-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85766-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85766-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85766-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85766-110">Attributes and Elements</span></span>  
 <span data-ttu-id="85766-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85766-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85766-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85766-112">Attributes</span></span>  
  
|<span data-ttu-id="85766-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="85766-113">Attribute</span></span>|<span data-ttu-id="85766-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="85766-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="85766-115">Каталог, где приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="85766-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85766-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85766-116">Child Elements</span></span>  
 <span data-ttu-id="85766-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85766-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85766-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85766-118">Parent Elements</span></span>  
  
|<span data-ttu-id="85766-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="85766-119">Element</span></span>|<span data-ttu-id="85766-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="85766-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85766-121">\<SMTP > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="85766-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="85766-122">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="85766-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85766-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="85766-123">Remarks</span></span>  
 <span data-ttu-id="85766-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="85766-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85766-125">Пример</span><span class="sxs-lookup"><span data-stu-id="85766-125">Example</span></span>  
 <span data-ttu-id="85766-126">Следующий пример определяет c:\maildrop как каталог раскладки почты.</span><span class="sxs-lookup"><span data-stu-id="85766-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85766-127">См. также</span><span class="sxs-lookup"><span data-stu-id="85766-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="85766-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="85766-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
