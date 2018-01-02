---
title: "&lt;сети&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d3e99a10403a735383ee5e1a78c1f85ac7fd8281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="22c37-102">&lt;сети&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="22c37-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="22c37-103">Настройка сетевых параметров для внешнего сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="22c37-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="22c37-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22c37-104">\<configuration></span></span>  
<span data-ttu-id="22c37-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="22c37-105">\<system.net></span></span>  
<span data-ttu-id="22c37-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="22c37-106">\<mailSettings></span></span>  
<span data-ttu-id="22c37-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="22c37-107">\<smtp></span></span>  
<span data-ttu-id="22c37-108">\<сети ></span><span class="sxs-lookup"><span data-stu-id="22c37-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c37-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22c37-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22c37-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22c37-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22c37-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22c37-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22c37-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22c37-112">Attributes</span></span>  
  
|<span data-ttu-id="22c37-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22c37-113">Attribute</span></span>|<span data-ttu-id="22c37-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="22c37-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="22c37-115">Указывает имя домена клиента для использования в запросом протокола SMTP для подключения к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="22c37-116">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="22c37-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="22c37-117">Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к почтовому серверу SMTP для SMTP-транзакций.</span><span class="sxs-lookup"><span data-stu-id="22c37-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="22c37-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="22c37-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="22c37-119">Указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="22c37-120">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="22c37-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="22c37-121">Указывает имя узла почтового SMTP-сервера для SMTP-транзакций.</span><span class="sxs-lookup"><span data-stu-id="22c37-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="22c37-122">Этот атрибут имеет значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22c37-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="22c37-123">Указывает пароль, используемый для проверки подлинности на SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="22c37-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="22c37-124">Этот атрибут имеет значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22c37-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="22c37-125">Указывает номер порта для подключения к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="22c37-126">Значение по умолчанию — 25.</span><span class="sxs-lookup"><span data-stu-id="22c37-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="22c37-127">Указывает имя поставщика службы (SPN) для проверки подлинности при использовании расширенной защиты для SMTP-транзакций.</span><span class="sxs-lookup"><span data-stu-id="22c37-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="22c37-128">Этот атрибут имеет значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22c37-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="22c37-129">Указывает имя пользователя для проверки подлинности на SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="22c37-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="22c37-130">Этот атрибут имеет значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22c37-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22c37-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22c37-131">Child Elements</span></span>  
 <span data-ttu-id="22c37-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22c37-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22c37-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22c37-133">Parent Elements</span></span>  
  
|<span data-ttu-id="22c37-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="22c37-134">Element</span></span>|<span data-ttu-id="22c37-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="22c37-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22c37-136">\<SMTP > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="22c37-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="22c37-137">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="22c37-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22c37-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="22c37-138">Remarks</span></span>  
 <span data-ttu-id="22c37-139">Некоторые SMTP требуют проверки подлинности на сервере, перед использованием.</span><span class="sxs-lookup"><span data-stu-id="22c37-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="22c37-140">Если вы хотите пройти проверку подлинности с помощью сетевые учетные данные по умолчанию на узле, задайте `defaultCredentials` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="22c37-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="22c37-141"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `defaultCredentials` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22c37-142">Можно также использовать обычную проверку подлинности (имя пользователя и пароль) для проверки подлинности на SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="22c37-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="22c37-143">Чтобы использовать этот параметр, необходимо указать допустимое имя пользователя и пароль для указанного сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22c37-144">Обычная проверка подлинности передает `userName` и `password` значения на сервер без шифрования.</span><span class="sxs-lookup"><span data-stu-id="22c37-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="22c37-145">Любой пользователь, наблюдение за сетевым трафиком можно просматривать свои учетные данные и использовать их для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="22c37-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="22c37-146">Следует рассмотреть возможность использования более безопасный механизм проверки подлинности, такие как Kerberos и NT LAN Manager (NTLM). Если `defaultCredentials` — `true`, Kerberos или NTLM используется, если сервер поддерживает эти протоколы.</span><span class="sxs-lookup"><span data-stu-id="22c37-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="22c37-147">Основные параметры проверки подлинности и по умолчанию сетевых учетных данных являются взаимоисключающими; Если задать `defaultCredentials` для `true` и укажите имя пользователя и пароль, использовать сетевые учетные данные по умолчанию и данные обычной проверки подлинности, учитываются.</span><span class="sxs-lookup"><span data-stu-id="22c37-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="22c37-148">Для обычной проверки подлинности, при указании `userName`, необходимо также указать `password` для проверки подлинности самостоятельно к почтовому серверу.</span><span class="sxs-lookup"><span data-stu-id="22c37-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="22c37-149"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `userName` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="22c37-150"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `password` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="22c37-151">Объект `password` атрибут будет обычно не вносится в файлах конфигурации, по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="22c37-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="22c37-152">`clientDomain` Атрибут изменяет имя домена клиента, используемое запросом протокола SMTP для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="22c37-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="22c37-153">`clientDomain` Атрибута может быть присвоено полное доменное имя локального компьютера, а не имя localhost, который используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22c37-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="22c37-154">Это обеспечивает большее соответствие стандартам протокола SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="22c37-155">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="22c37-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="22c37-156"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `clientDomain` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22c37-157">`targetName` Атрибут используется для проверки подлинности при использовании расширенной защиты.</span><span class="sxs-lookup"><span data-stu-id="22c37-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="22c37-158">Значение по умолчанию имеет форму «SMTPSVC /\<узла >» где \<узла > — имя узла почтового SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="22c37-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="22c37-159"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `targetName` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22c37-160">`enableSsl` Атрибут указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="22c37-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="22c37-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Класс поддерживает только расширения службы SMTP для защиты SMTP через протокол TLS как определено в документе RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="22c37-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="22c37-162">В этом режиме сеанс SMTP начинается в незашифрованном канале, а затем выдает команды STARTTLS клиента на сервере, чтобы переключиться на безопасное соединение с помощью протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="22c37-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="22c37-163">См. в RFC 3207 публикации по IETF Internet Engineering Task Force () для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="22c37-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="22c37-164">Альтернативный способ подключения — где сеанс SSL устанавливается заранее перед любой протокол отправки команд.</span><span class="sxs-lookup"><span data-stu-id="22c37-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="22c37-165">Этот способ подключения иногда называют SMTPS и по умолчанию используется порт 465.</span><span class="sxs-lookup"><span data-stu-id="22c37-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="22c37-166">Это альтернативный способ подключения с помощью протокола SSL в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="22c37-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="22c37-167"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения `enableSsl` атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22c37-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22c37-168">Пример</span><span class="sxs-lookup"><span data-stu-id="22c37-168">Example</span></span>  
 <span data-ttu-id="22c37-169">Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты с помощью сетевые учетные данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22c37-169">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22c37-170">См. также</span><span class="sxs-lookup"><span data-stu-id="22c37-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="22c37-171">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="22c37-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
