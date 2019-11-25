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
ms.openlocfilehash: 1acc724bb14c3610f14d06452c30b3d5dac42e13
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089078"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="e3ed8-102">Элемент \<СпеЦифиедпиккупдиректори > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="e3ed8-103">Настраивает локальный каталог для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="e3ed8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e3ed8-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e3ed8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<маилсеттингс >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="e3ed8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="e3ed8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<спеЦифиедпиккупдиректори >**</span><span class="sxs-lookup"><span data-stu-id="e3ed8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ed8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3ed8-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3ed8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3ed8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e3ed8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3ed8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3ed8-112">Attributes</span></span>  
  
|<span data-ttu-id="e3ed8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3ed8-113">Attribute</span></span>|<span data-ttu-id="e3ed8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e3ed8-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="e3ed8-115">Каталог, в котором приложения сохраняют электронную почту для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3ed8-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3ed8-116">Child Elements</span></span>  
 <span data-ttu-id="e3ed8-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3ed8-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3ed8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3ed8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3ed8-119">Element</span></span>|<span data-ttu-id="e3ed8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e3ed8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3ed8-121">Элемент > SMTP \<(параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e3ed8-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="e3ed8-122">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3ed8-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="e3ed8-123">Remarks</span></span>  
 <span data-ttu-id="e3ed8-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3ed8-125">Пример</span><span class="sxs-lookup"><span data-stu-id="e3ed8-125">Example</span></span>  
 <span data-ttu-id="e3ed8-126">В следующем примере в качестве каталога подбора почты указывается к:\маилдроп.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3ed8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ed8-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="e3ed8-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e3ed8-128">Network Settings Schema</span></span>](index.md)
