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
ms.openlocfilehash: b8ea08cbd76e60a3665703bc50924dd94500cd87
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659322"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="0b1ad-102">\<Элемент > Маилсеттингс (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="0b1ad-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="0b1ad-103">Настраивает параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-103">Configures mail sending options.</span></span>  

<span data-ttu-id="0b1ad-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0b1ad-104">\<configuration></span></span>  
<span data-ttu-id="0b1ad-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="0b1ad-105">\<system.net></span></span>  
<span data-ttu-id="0b1ad-106">\<Маилсеттингс ></span><span class="sxs-lookup"><span data-stu-id="0b1ad-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1ad-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b1ad-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b1ad-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b1ad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0b1ad-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b1ad-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b1ad-110">Attributes</span></span>  
 <span data-ttu-id="0b1ad-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b1ad-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b1ad-112">Child Elements</span></span>  
  
|<span data-ttu-id="0b1ad-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b1ad-113">Attribute</span></span>|<span data-ttu-id="0b1ad-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0b1ad-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="0b1ad-115">\<Элемент > SMTP (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="0b1ad-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="0b1ad-116">Настраивает параметры протокола простого почтового транспорта.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b1ad-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b1ad-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0b1ad-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="0b1ad-118">**Element**</span></span>|<span data-ttu-id="0b1ad-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b1ad-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0b1ad-120">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="0b1ad-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="0b1ad-121">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b1ad-122">Пример</span><span class="sxs-lookup"><span data-stu-id="0b1ad-122">Example</span></span>  
 <span data-ttu-id="0b1ad-123">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b1ad-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0b1ad-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0b1ad-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="0b1ad-125">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="0b1ad-125">Network Settings Schema</span></span>](index.md)
