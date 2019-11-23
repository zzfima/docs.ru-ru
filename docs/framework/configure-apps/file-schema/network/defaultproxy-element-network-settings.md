---
title: Элемент <defaultProxy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698205"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="61377-102">Элемент \<defaultProxy > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="61377-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="61377-103">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="61377-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[<span data-ttu-id="61377-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="61377-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="61377-105">&nbsp;&nbsp;[ **\<System. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="61377-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="61377-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultProxy >**</span><span class="sxs-lookup"><span data-stu-id="61377-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61377-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61377-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61377-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61377-108">Attributes and Elements</span></span>  
 <span data-ttu-id="61377-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61377-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61377-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61377-110">Attributes</span></span>  
  
|<span data-ttu-id="61377-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="61377-111">**Element**</span></span>|<span data-ttu-id="61377-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="61377-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="61377-113">Указывает, используется ли веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="61377-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="61377-114">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="61377-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="61377-115">Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="61377-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="61377-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="61377-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61377-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61377-117">Child Elements</span></span>  
  
|<span data-ttu-id="61377-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="61377-118">**Element**</span></span>|<span data-ttu-id="61377-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="61377-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="61377-120">бипасслист</span><span class="sxs-lookup"><span data-stu-id="61377-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="61377-121">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="61377-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="61377-122">module</span><span class="sxs-lookup"><span data-stu-id="61377-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="61377-123">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="61377-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="61377-124">-</span><span class="sxs-lookup"><span data-stu-id="61377-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="61377-125">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="61377-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61377-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61377-126">Parent Elements</span></span>  
  
|<span data-ttu-id="61377-127">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="61377-127">**Element**</span></span>|<span data-ttu-id="61377-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="61377-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="61377-129">system.net</span><span class="sxs-lookup"><span data-stu-id="61377-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="61377-130">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="61377-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61377-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="61377-131">Remarks</span></span>  
 <span data-ttu-id="61377-132">Если элемент defaultProxy пуст, будут использоваться параметры прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="61377-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="61377-133">Это поведение отличается от поведения в .NET Framework версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="61377-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="61377-134">Исключение возникает, если элемент [module](module-element-network-settings.md) задает тип, отличный от Public, тип не является производным от класса <xref:System.Net.IWebProxy>, возникло исключение из конструктора без параметров данного объекта или произошло исключение при получении указанного системой прокси-сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61377-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="61377-135">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="61377-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="61377-136">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="61377-136">Configuration Files</span></span>  
 <span data-ttu-id="61377-137">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="61377-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61377-138">Пример</span><span class="sxs-lookup"><span data-stu-id="61377-138">Example</span></span>  
 <span data-ttu-id="61377-139">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа и contoso.com.</span><span class="sxs-lookup"><span data-stu-id="61377-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61377-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="61377-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="61377-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="61377-141">Network Settings Schema</span></span>](index.md)
