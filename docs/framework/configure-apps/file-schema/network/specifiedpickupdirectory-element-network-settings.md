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
ms.openlocfilehash: 6abee1b01e690633dabfd225b30fcb9b8b408dad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270827"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="d8abb-102">\<specifiedPickupDirectory > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="d8abb-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="d8abb-103">Настраивает локальный каталог для сервера транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="d8abb-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="d8abb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d8abb-104">\<configuration></span></span>  
<span data-ttu-id="d8abb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d8abb-105">\<system.net></span></span>  
<span data-ttu-id="d8abb-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="d8abb-106">\<mailSettings></span></span>  
<span data-ttu-id="d8abb-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="d8abb-107">\<smtp></span></span>  
<span data-ttu-id="d8abb-108">\<specifiedPickupDirectory ></span><span class="sxs-lookup"><span data-stu-id="d8abb-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8abb-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8abb-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8abb-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8abb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8abb-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8abb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8abb-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8abb-112">Attributes</span></span>  
  
|<span data-ttu-id="d8abb-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d8abb-113">Attribute</span></span>|<span data-ttu-id="d8abb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d8abb-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="d8abb-115">Каталог, в которой приложения сохраняют сообщения электронной почты для последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="d8abb-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8abb-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8abb-116">Child Elements</span></span>  
 <span data-ttu-id="d8abb-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d8abb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8abb-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8abb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d8abb-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8abb-119">Element</span></span>|<span data-ttu-id="d8abb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d8abb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8abb-121">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="d8abb-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="d8abb-122">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="d8abb-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8abb-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8abb-123">Remarks</span></span>  
 <span data-ttu-id="d8abb-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="d8abb-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8abb-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d8abb-125">Example</span></span>  
 <span data-ttu-id="d8abb-126">Следующий пример определяет c:\maildrop как каталог раскладки почты.</span><span class="sxs-lookup"><span data-stu-id="d8abb-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8abb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d8abb-127">See also</span></span>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="d8abb-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d8abb-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
