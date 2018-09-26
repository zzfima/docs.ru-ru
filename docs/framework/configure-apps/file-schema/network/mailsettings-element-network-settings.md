---
title: '&lt;mailSettings&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f3a706edaeba551139368568a7467e0cdab3524c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208598"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="233fe-102">&lt;mailSettings&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="233fe-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="233fe-103">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="233fe-103">Configures mail sending options.</span></span>  

<span data-ttu-id="233fe-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="233fe-104">\<configuration></span></span>  
<span data-ttu-id="233fe-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="233fe-105">\<system.net></span></span>  
<span data-ttu-id="233fe-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="233fe-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="233fe-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="233fe-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="233fe-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="233fe-108">Attributes and Elements</span></span>  
 <span data-ttu-id="233fe-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="233fe-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="233fe-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="233fe-110">Attributes</span></span>  
 <span data-ttu-id="233fe-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="233fe-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="233fe-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="233fe-112">Child Elements</span></span>  
  
|<span data-ttu-id="233fe-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="233fe-113">Attribute</span></span>|<span data-ttu-id="233fe-114">Описание</span><span class="sxs-lookup"><span data-stu-id="233fe-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="233fe-115">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="233fe-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="233fe-116">Служит для настройки параметров простой протокол транспорта почты.</span><span class="sxs-lookup"><span data-stu-id="233fe-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="233fe-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="233fe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="233fe-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="233fe-118">**Element**</span></span>|<span data-ttu-id="233fe-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="233fe-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="233fe-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="233fe-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="233fe-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="233fe-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="233fe-122">Пример</span><span class="sxs-lookup"><span data-stu-id="233fe-122">Example</span></span>  
 <span data-ttu-id="233fe-123">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="233fe-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="233fe-124">См. также</span><span class="sxs-lookup"><span data-stu-id="233fe-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="233fe-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="233fe-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
