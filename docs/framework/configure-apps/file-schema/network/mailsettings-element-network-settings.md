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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089233"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="c8a8a-102">Элемент \<Маилсеттингс > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="c8a8a-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="c8a8a-103">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-103">Configures mail sending options.</span></span>  

<span data-ttu-id="c8a8a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8a8a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8a8a-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8a8a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c8a8a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<маилсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="c8a8a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c8a8a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8a8a-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8a8a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8a8a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c8a8a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8a8a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8a8a-110">Attributes</span></span>  
 <span data-ttu-id="c8a8a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8a8a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8a8a-112">Child Elements</span></span>  
  
|<span data-ttu-id="c8a8a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8a8a-113">Attribute</span></span>|<span data-ttu-id="c8a8a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c8a8a-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c8a8a-115">Элемент > SMTP \<(параметры сети)</span><span class="sxs-lookup"><span data-stu-id="c8a8a-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="c8a8a-116">Настраивает параметры протокола простого почтового транспорта.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8a8a-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8a8a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c8a8a-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="c8a8a-118">**Element**</span></span>|<span data-ttu-id="c8a8a-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c8a8a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c8a8a-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="c8a8a-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c8a8a-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8a8a-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c8a8a-122">Example</span></span>  
 <span data-ttu-id="c8a8a-123">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8a8a-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8a8a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c8a8a-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="c8a8a-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="c8a8a-125">Network Settings Schema</span></span>](index.md)
