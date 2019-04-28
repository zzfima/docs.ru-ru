---
title: Элемент <mailSettings> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 54fb68ab0bf8aa2665d70391350c626131ccb4bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674510"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="01050-102">\<mailSettings > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="01050-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="01050-103">Настраивает параметры отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="01050-103">Configures mail sending options.</span></span>  

<span data-ttu-id="01050-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01050-104">\<configuration></span></span>  
<span data-ttu-id="01050-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="01050-105">\<system.net></span></span>  
<span data-ttu-id="01050-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="01050-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01050-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01050-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01050-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="01050-108">Attributes and Elements</span></span>  
 <span data-ttu-id="01050-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="01050-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01050-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="01050-110">Attributes</span></span>  
 <span data-ttu-id="01050-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="01050-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="01050-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="01050-112">Child Elements</span></span>  
  
|<span data-ttu-id="01050-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="01050-113">Attribute</span></span>|<span data-ttu-id="01050-114">Описание</span><span class="sxs-lookup"><span data-stu-id="01050-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="01050-115">\<SMTP > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="01050-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="01050-116">Служит для настройки параметров простой протокол транспорта почты.</span><span class="sxs-lookup"><span data-stu-id="01050-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01050-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="01050-117">Parent Elements</span></span>  
  
|<span data-ttu-id="01050-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="01050-118">**Element**</span></span>|<span data-ttu-id="01050-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="01050-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01050-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="01050-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="01050-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="01050-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="01050-122">Пример</span><span class="sxs-lookup"><span data-stu-id="01050-122">Example</span></span>  
 <span data-ttu-id="01050-123">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="01050-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01050-124">См. также</span><span class="sxs-lookup"><span data-stu-id="01050-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="01050-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="01050-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
