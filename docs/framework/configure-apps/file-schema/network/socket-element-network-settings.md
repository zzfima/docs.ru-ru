---
title: Элемент <socket> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: aa455945b839ada4100138d5bdf9fc239376e5cb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663983"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="2ea5c-102">\<Элемент > сокета (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2ea5c-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="2ea5c-103">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="2ea5c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2ea5c-104">\<configuration></span></span>  
<span data-ttu-id="2ea5c-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="2ea5c-105">\<system.net></span></span>  
<span data-ttu-id="2ea5c-106">\<> параметров</span><span class="sxs-lookup"><span data-stu-id="2ea5c-106">\<settings></span></span>  
<span data-ttu-id="2ea5c-107">\<> сокета</span><span class="sxs-lookup"><span data-stu-id="2ea5c-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea5c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ea5c-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ea5c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ea5c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ea5c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ea5c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ea5c-111">Attributes</span></span>  
  
|<span data-ttu-id="2ea5c-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="2ea5c-112">**Attribute**</span></span>|<span data-ttu-id="2ea5c-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ea5c-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="2ea5c-114">Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Accept.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="2ea5c-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="2ea5c-116">Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Connect.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="2ea5c-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="2ea5c-118">Указывает значение по <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> умолчанию, используемое для сокета.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="2ea5c-119">Значение по умолчанию зависит от версии Windows.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ea5c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ea5c-120">Child Elements</span></span>  
 <span data-ttu-id="2ea5c-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ea5c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ea5c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2ea5c-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2ea5c-123">**Element**</span></span>|<span data-ttu-id="2ea5c-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ea5c-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2ea5c-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ea5c-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="2ea5c-126">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ea5c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ea5c-127">Remarks</span></span>  
 <span data-ttu-id="2ea5c-128">Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в отношении использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="2ea5c-129">Порты завершения рекомендуются для высокопроизводительных серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="2ea5c-130">По умолчанию для `alwaysUseCompletionPortsForAccept` атрибутов и `alwaysUseCompletionPortsForConnect` задано значение **false**.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="2ea5c-131">Можно использовать для получения текущего значения `alwaysUseCompletionPortsForAccept` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A></span><span class="sxs-lookup"><span data-stu-id="2ea5c-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="2ea5c-132">Можно использовать для получения текущего значения `alwaysUseCompletionPortsForConnect` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A></span><span class="sxs-lookup"><span data-stu-id="2ea5c-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="2ea5c-133">Атрибут указывает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> , используемое для сокета. `ipProtectionLevel`</span><span class="sxs-lookup"><span data-stu-id="2ea5c-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="2ea5c-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Свойство позволяет настроить ограничение сокета IPv6 на указанную область, например адреса с одинаковой локальной ссылкой или локальным префиксом сайта.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="2ea5c-135">Этот параметр позволяет приложениям размещать ограничения доступа к сокетам IPv6.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="2ea5c-136">Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="2ea5c-137">Этот параметр расширяет или ограничивает область действия прослушивающего сокета, обеспечивая неограниченный доступ от общедоступных и частных пользователей при необходимости или ограничивающий доступ только для того же сайта, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="2ea5c-138">Этот `ipProtectionLevel` параметр атрибута влияет только на первоначальный входящий трафик.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="2ea5c-139">TCP-сервер, прослушивающий входящие подключения на сокете.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="2ea5c-140">Приложение UDP, получающее пакет на сокете.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="2ea5c-141">Этот параметр конфигурации не влияет на уже установленные TCP-подключения (трафик в обоих направлениях не ограничен) и не влияет на приложение, отправляющее пакеты UDP.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="2ea5c-142">Возможные значения для `ipProtectionLevel` параметра атрибута соответствуют определенным уровням защиты, указанным <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> в перечислении, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ea5c-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="2ea5c-143">**Значение атрибута**</span><span class="sxs-lookup"><span data-stu-id="2ea5c-143">**Attribute Value**</span></span>|<span data-ttu-id="2ea5c-144">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ea5c-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="2ea5c-145">еджерестриктед</span><span class="sxs-lookup"><span data-stu-id="2ea5c-145">EdgeRestricted</span></span>|<span data-ttu-id="2ea5c-146">Уровень защиты IP ограничен границей.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="2ea5c-147">Это значение будет использоваться приложениями, предназначенными для взаимодействия через Интернет.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="2ea5c-148">Этот параметр не разрешает обход преобразования сетевых адресов (NAT) с помощью реализации Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="2ea5c-149">Эти приложения могут обходить брандмауэры IPv4, поэтому приложения должны быть защищены от Интернет-атак, направленных на открытый порт.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="2ea5c-150">В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP на сокете ограничено границей.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="2ea5c-151">Ограничено</span><span class="sxs-lookup"><span data-stu-id="2ea5c-151">Restricted</span></span>|<span data-ttu-id="2ea5c-152">Уровень защиты IP-адресов ограничен.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-152">The IP protection level is restricted.</span></span> <span data-ttu-id="2ea5c-153">Это значение будет использоваться приложениями интрасети, которые не реализуют сценарии Интернета.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="2ea5c-154">Обычно эти приложения не тестируются и не защищаются от атак в стиле Интернета.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="2ea5c-155">Этот параметр ограничит полученный трафик только локальным каналом.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="2ea5c-156">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="2ea5c-156">Unrestricted</span></span>|<span data-ttu-id="2ea5c-157">Уровень защиты IP-адресов не ограничен.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="2ea5c-158">Это значение будет использоваться приложениями, предназначенными для работы через Интернет, включая приложения, использующие возможности просмотра NAT IPv6, встроенные в Windows (например, Teredo).</span><span class="sxs-lookup"><span data-stu-id="2ea5c-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="2ea5c-159">Эти приложения могут обходить брандмауэры IPv4, поэтому приложения должны быть защищены от Интернет-атак, направленных на открытый порт.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="2ea5c-160">В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP-адресов на сокете не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="2ea5c-161">Не указан</span><span class="sxs-lookup"><span data-stu-id="2ea5c-161">Unspecified</span></span>|<span data-ttu-id="2ea5c-162">Уровень защиты IP-адресов не указан.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="2ea5c-163">В Windows 7 и Windows Server 2008 R2 значение по умолчанию для уровня защиты IP-адресов на сокете не указано.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="2ea5c-164">Значение по умолчанию для `ipProtectionLevel` атрибута не **указано**.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="2ea5c-165">Свойство можно использовать для получения текущего значения `ipProtectionLevel` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A></span><span class="sxs-lookup"><span data-stu-id="2ea5c-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2ea5c-166">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2ea5c-166">Configuration Files</span></span>  
 <span data-ttu-id="2ea5c-167">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2ea5c-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ea5c-168">Пример</span><span class="sxs-lookup"><span data-stu-id="2ea5c-168">Example</span></span>  
 <span data-ttu-id="2ea5c-169">В следующем примере показано, как указать, что порты завершения должны использоваться и что значение по <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> умолчанию должно быть неограниченным.</span><span class="sxs-lookup"><span data-stu-id="2ea5c-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ea5c-170">См. также</span><span class="sxs-lookup"><span data-stu-id="2ea5c-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="2ea5c-171">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2ea5c-171">Network Settings Schema</span></span>](index.md)
