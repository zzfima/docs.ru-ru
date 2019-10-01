---
title: Элемент <specifiedPickupDirectory> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697595"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="bd1dc-102">Элемент > @no__t 0specifiedPickupDirectory (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="bd1dc-103">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="bd1dc-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bd1dc-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bd1dc-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="bd1dc-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="bd1dc-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="bd1dc-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1dc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd1dc-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd1dc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bd1dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd1dc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd1dc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bd1dc-112">Attributes</span></span>  
  
|<span data-ttu-id="bd1dc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bd1dc-113">Attribute</span></span>|<span data-ttu-id="bd1dc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bd1dc-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="bd1dc-115">Каталог, в котором приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd1dc-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bd1dc-116">Child Elements</span></span>  
 <span data-ttu-id="bd1dc-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd1dc-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bd1dc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bd1dc-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd1dc-119">Element</span></span>|<span data-ttu-id="bd1dc-120">Описание</span><span class="sxs-lookup"><span data-stu-id="bd1dc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd1dc-121">Элемент > @no__t 1smtp (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="bd1dc-122">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd1dc-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd1dc-123">Remarks</span></span>  
 <span data-ttu-id="bd1dc-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd1dc-125">Пример</span><span class="sxs-lookup"><span data-stu-id="bd1dc-125">Example</span></span>  
 <span data-ttu-id="bd1dc-126">В следующем примере в качестве каталога подбора почты указывается к:\маилдроп.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd1dc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bd1dc-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="bd1dc-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="bd1dc-128">Network Settings Schema</span></span>](index.md)
