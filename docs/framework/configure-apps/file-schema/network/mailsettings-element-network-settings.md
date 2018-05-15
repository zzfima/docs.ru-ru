---
title: '&lt;mailSettings&gt; элемент (параметры сети)'
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
ms.openlocfilehash: 5bc7cc649b18a5330d056bbddfe96db4ecca2ec8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="03a32-102">&lt;mailSettings&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="03a32-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="03a32-103">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="03a32-103">Configures mail sending options.</span></span>  

<span data-ttu-id="03a32-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03a32-104">\<configuration></span></span>  
<span data-ttu-id="03a32-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="03a32-105">\<system.net></span></span>  
<span data-ttu-id="03a32-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="03a32-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a32-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03a32-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03a32-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="03a32-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03a32-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03a32-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03a32-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03a32-110">Attributes</span></span>  
 <span data-ttu-id="03a32-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="03a32-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03a32-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03a32-112">Child Elements</span></span>  
  
|<span data-ttu-id="03a32-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="03a32-113">Attribute</span></span>|<span data-ttu-id="03a32-114">Описание</span><span class="sxs-lookup"><span data-stu-id="03a32-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="03a32-115">\<SMTP > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="03a32-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="03a32-116">Настраивает параметры простой протокол передачи почты.</span><span class="sxs-lookup"><span data-stu-id="03a32-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03a32-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03a32-117">Parent Elements</span></span>  
  
|<span data-ttu-id="03a32-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="03a32-118">**Element**</span></span>|<span data-ttu-id="03a32-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="03a32-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="03a32-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="03a32-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="03a32-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="03a32-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03a32-122">Пример</span><span class="sxs-lookup"><span data-stu-id="03a32-122">Example</span></span>  
 <span data-ttu-id="03a32-123">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03a32-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
  
## <a name="see-also"></a><span data-ttu-id="03a32-124">См. также</span><span class="sxs-lookup"><span data-stu-id="03a32-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="03a32-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="03a32-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
