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
manager: markl
ms.openlocfilehash: a9afd992a12392ae0ad1c27eea305cb7e367686d
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874420"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="41913-102">&lt;mailSettings&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="41913-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="41913-103">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="41913-103">Configures mail sending options.</span></span>  

<span data-ttu-id="41913-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="41913-104">\<configuration></span></span>  
<span data-ttu-id="41913-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="41913-105">\<system.net></span></span>  
<span data-ttu-id="41913-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="41913-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41913-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41913-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41913-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41913-108">Attributes and Elements</span></span>  
 <span data-ttu-id="41913-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="41913-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41913-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41913-110">Attributes</span></span>  
 <span data-ttu-id="41913-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="41913-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41913-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41913-112">Child Elements</span></span>  
  
|<span data-ttu-id="41913-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="41913-113">Attribute</span></span>|<span data-ttu-id="41913-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="41913-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="41913-115">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="41913-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="41913-116">Служит для настройки параметров простой протокол транспорта почты.</span><span class="sxs-lookup"><span data-stu-id="41913-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41913-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41913-117">Parent Elements</span></span>  
  
|<span data-ttu-id="41913-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="41913-118">**Element**</span></span>|<span data-ttu-id="41913-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="41913-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="41913-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="41913-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="41913-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="41913-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="41913-122">Пример</span><span class="sxs-lookup"><span data-stu-id="41913-122">Example</span></span>  
 <span data-ttu-id="41913-123">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41913-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41913-124">См. также</span><span class="sxs-lookup"><span data-stu-id="41913-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="41913-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="41913-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
