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
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154612"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="5be8c-102">\<specifiedPickupDirectory> элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="5be8c-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="5be8c-103">Настраивает локальный каталог для сервера Простого почтового транспортного протокола (SMTP).</span><span class="sxs-lookup"><span data-stu-id="5be8c-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="5be8c-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5be8c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5be8c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5be8c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="5be8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5be8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="5be8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5be8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="5be8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span><span class="sxs-lookup"><span data-stu-id="5be8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be8c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5be8c-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be8c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5be8c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5be8c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5be8c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be8c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5be8c-112">Attributes</span></span>  
  
|<span data-ttu-id="5be8c-113">attribute</span><span class="sxs-lookup"><span data-stu-id="5be8c-113">Attribute</span></span>|<span data-ttu-id="5be8c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5be8c-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="5be8c-115">Каталог, где приложения сохраняют электронную почту для последующей обработки сервером SMTP.</span><span class="sxs-lookup"><span data-stu-id="5be8c-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be8c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5be8c-116">Child Elements</span></span>  
 <span data-ttu-id="5be8c-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="5be8c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5be8c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5be8c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5be8c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5be8c-119">Element</span></span>|<span data-ttu-id="5be8c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5be8c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be8c-121">\<smtp> Элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="5be8c-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="5be8c-122">Настраивает опции отправки почты Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="5be8c-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5be8c-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="5be8c-123">Remarks</span></span>  
 <span data-ttu-id="5be8c-124">Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="5be8c-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5be8c-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5be8c-125">Example</span></span>  
 <span data-ttu-id="5be8c-126">В следующем примере указывается c: 'maildrop как каталог почтовых пикапов.</span><span class="sxs-lookup"><span data-stu-id="5be8c-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5be8c-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5be8c-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="5be8c-128">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="5be8c-128">Network Settings Schema</span></span>](index.md)
