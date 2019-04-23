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
ms.openlocfilehash: 82bfe3b6e3107ff787716657dbf0b31dcadde911
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160164"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="a5faf-102">\<сокет > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="a5faf-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="a5faf-103">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="a5faf-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="a5faf-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a5faf-104">\<configuration></span></span>  
<span data-ttu-id="a5faf-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a5faf-105">\<system.net></span></span>  
<span data-ttu-id="a5faf-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="a5faf-106">\<settings></span></span>  
<span data-ttu-id="a5faf-107">\<сокет ></span><span class="sxs-lookup"><span data-stu-id="a5faf-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5faf-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5faf-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5faf-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a5faf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5faf-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a5faf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5faf-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a5faf-111">Attributes</span></span>  
  
|<span data-ttu-id="a5faf-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="a5faf-112">**Attribute**</span></span>|<span data-ttu-id="a5faf-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a5faf-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="a5faf-114">Указывает, всегда ли сокет использует порты завершения для вызовы метода приема.</span><span class="sxs-lookup"><span data-stu-id="a5faf-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="a5faf-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a5faf-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="a5faf-116">Указывает, всегда ли сокет использует порты завершения для вызовов метода Connect.</span><span class="sxs-lookup"><span data-stu-id="a5faf-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="a5faf-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a5faf-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="a5faf-118">Указывает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> для сокета.</span><span class="sxs-lookup"><span data-stu-id="a5faf-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="a5faf-119">Значение по умолчанию зависит от версии Windows.</span><span class="sxs-lookup"><span data-stu-id="a5faf-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5faf-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a5faf-120">Child Elements</span></span>  
 <span data-ttu-id="a5faf-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a5faf-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5faf-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a5faf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a5faf-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a5faf-123">**Element**</span></span>|<span data-ttu-id="a5faf-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a5faf-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a5faf-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5faf-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="a5faf-126">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a5faf-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5faf-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5faf-127">Remarks</span></span>  
 <span data-ttu-id="a5faf-128">Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в отношении использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5faf-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="a5faf-129">Порты завершения рекомендуется использовать для высокопроизводительных серверных приложений.</span><span class="sxs-lookup"><span data-stu-id="a5faf-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="a5faf-130">Значение по умолчанию для `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` атрибутов **false**.</span><span class="sxs-lookup"><span data-stu-id="a5faf-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="a5faf-131"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> Можно использовать для получения текущего значения `alwaysUseCompletionPortsForAccept` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5faf-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="a5faf-132"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> Можно использовать для получения текущего значения `alwaysUseCompletionPortsForConnect` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5faf-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="a5faf-133">`ipProtectionLevel` Атрибут указывает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> для сокета.</span><span class="sxs-lookup"><span data-stu-id="a5faf-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="a5faf-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Свойство позволяет настроить ограничение для сокет IPv6 указанным диапазоном, такие как адреса, с тем же связи, локальных или локальным префиксом сайта.</span><span class="sxs-lookup"><span data-stu-id="a5faf-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="a5faf-135">Этот параметр позволяет приложениям устанавливать ограничения доступа к сокетам IPv6.</span><span class="sxs-lookup"><span data-stu-id="a5faf-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="a5faf-136">Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак.</span><span class="sxs-lookup"><span data-stu-id="a5faf-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="a5faf-137">Этот параметр расширяет или сужает диапазон прослушивающего сокета, включение неограниченный доступ со стороны открытых и закрытых пользователей, когда это необходимо, или ограничить доступ только для одного сайта и при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a5faf-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="a5faf-138">Это `ipProtectionLevel` атрибут влияет только начального входящего трафика:</span><span class="sxs-lookup"><span data-stu-id="a5faf-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="a5faf-139">TCP-сервер, прослушивание входящих подключений через сокет.</span><span class="sxs-lookup"><span data-stu-id="a5faf-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="a5faf-140">Приложение UDP, получения пакета на сокете.</span><span class="sxs-lookup"><span data-stu-id="a5faf-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="a5faf-141">Этот параметр конфигурации не влияет на уже установленные TCP-соединения, (трафик не ограничен в обоих направлениях) и не влияет на приложения, отправляющие пакеты UDP.</span><span class="sxs-lookup"><span data-stu-id="a5faf-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="a5faf-142">Возможные значения `ipProtectionLevel` соответствуют параметры атрибутов с уровнями защиты определенных, указанный в <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> перечисления следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a5faf-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="a5faf-143">**Значение атрибута**</span><span class="sxs-lookup"><span data-stu-id="a5faf-143">**Attribute Value**</span></span>|<span data-ttu-id="a5faf-144">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a5faf-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="a5faf-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="a5faf-145">EdgeRestricted</span></span>|<span data-ttu-id="a5faf-146">Уровень защиты IP — предельно ограничено.</span><span class="sxs-lookup"><span data-stu-id="a5faf-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="a5faf-147">Это значение используется приложениями, разработанными для работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a5faf-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="a5faf-148">Этот параметр не допуская сетевых адресов (NAT) с помощью реализации Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="a5faf-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="a5faf-149">Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от Интернет-атак, направленных на открытый порт.</span><span class="sxs-lookup"><span data-stu-id="a5faf-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="a5faf-150">В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP сокета — предельно ограничено.</span><span class="sxs-lookup"><span data-stu-id="a5faf-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="a5faf-151">Ограничено</span><span class="sxs-lookup"><span data-stu-id="a5faf-151">Restricted</span></span>|<span data-ttu-id="a5faf-152">Уровень защиты IP — ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="a5faf-152">The IP protection level is restricted.</span></span> <span data-ttu-id="a5faf-153">Это значение будет использоваться приложениями интрасети, не работающих в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a5faf-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="a5faf-154">Эти приложения обычно не протестированы и не защищаются против атак из Интернета.</span><span class="sxs-lookup"><span data-stu-id="a5faf-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="a5faf-155">Этот параметр ограничивает получаемый трафик локальным.</span><span class="sxs-lookup"><span data-stu-id="a5faf-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="a5faf-156">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="a5faf-156">Unrestricted</span></span>|<span data-ttu-id="a5faf-157">Уровень защиты IP — неограниченно.</span><span class="sxs-lookup"><span data-stu-id="a5faf-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="a5faf-158">Это значение будет использоваться приложениями, разработанными для работы в Интернете, включая приложения, использующие возможности обхода IPv6 NAT в Windows (например, Teredo).</span><span class="sxs-lookup"><span data-stu-id="a5faf-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="a5faf-159">Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от Интернет-атак, направленных на открытый порт.</span><span class="sxs-lookup"><span data-stu-id="a5faf-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="a5faf-160">В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP сокета — неограниченно.</span><span class="sxs-lookup"><span data-stu-id="a5faf-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="a5faf-161">Не указан</span><span class="sxs-lookup"><span data-stu-id="a5faf-161">Unspecified</span></span>|<span data-ttu-id="a5faf-162">Уровень защиты IP не определен.</span><span class="sxs-lookup"><span data-stu-id="a5faf-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="a5faf-163">В Windows 7 и Windows Server 2008 R2 значение по умолчанию для уровня защиты IP сокета не определен.</span><span class="sxs-lookup"><span data-stu-id="a5faf-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="a5faf-164">Значение по умолчанию для `ipProtectionLevel` атрибут **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="a5faf-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="a5faf-165"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Свойство может использоваться для получения текущего значения `ipProtectionLevel` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5faf-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a5faf-166">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5faf-166">Configuration Files</span></span>  
 <span data-ttu-id="a5faf-167">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a5faf-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5faf-168">Пример</span><span class="sxs-lookup"><span data-stu-id="a5faf-168">Example</span></span>  
 <span data-ttu-id="a5faf-169">В следующем примере показано, как указать, что следует использовать порты завершения и, по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> должно быть не ограничено.</span><span class="sxs-lookup"><span data-stu-id="a5faf-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5faf-170">См. также</span><span class="sxs-lookup"><span data-stu-id="a5faf-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="a5faf-171">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a5faf-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
