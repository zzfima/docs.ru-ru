---
title: Элемент <network> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154820"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="34ffd-102">\<сетевой элемент> (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="34ffd-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="34ffd-103">Настраивает параметры сети для внешнего сервера Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="34ffd-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="34ffd-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34ffd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34ffd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="34ffd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="34ffd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="34ffd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="34ffd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="34ffd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="34ffd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сети>**</span><span class="sxs-lookup"><span data-stu-id="34ffd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="34ffd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34ffd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34ffd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="34ffd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34ffd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="34ffd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34ffd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="34ffd-112">Attributes</span></span>  
  
|<span data-ttu-id="34ffd-113">attribute</span><span class="sxs-lookup"><span data-stu-id="34ffd-113">Attribute</span></span>|<span data-ttu-id="34ffd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="34ffd-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="34ffd-115">Упогоняет доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="34ffd-116">Значение по умолчанию — это локальное имя локального компьютера, отправляя запрос.</span><span class="sxs-lookup"><span data-stu-id="34ffd-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="34ffd-117">Уточняется, следует ли использовать учетные данные пользователей по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="34ffd-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="34ffd-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="34ffd-119">Уточняется, используется ли SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="34ffd-120">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="34ffd-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="34ffd-121">Упогоняет имя почтового сервера SMTP для использования для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="34ffd-122">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="34ffd-123">Упогоняет пароль для использования для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="34ffd-124">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="34ffd-125">Определяет номер порта для подключения к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="34ffd-126">По умолчанию используется значение 25.</span><span class="sxs-lookup"><span data-stu-id="34ffd-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="34ffd-127">Учреждать имя поставщика услуг (SPN) для использования для проверки подлинности при использовании расширенной защиты для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="34ffd-128">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="34ffd-129">Упогоняет имя пользователя для использования для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="34ffd-130">Этот атрибут не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34ffd-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="34ffd-131">Child Elements</span></span>  
 <span data-ttu-id="34ffd-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="34ffd-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34ffd-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="34ffd-133">Parent Elements</span></span>  
  
|<span data-ttu-id="34ffd-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="34ffd-134">Element</span></span>|<span data-ttu-id="34ffd-135">Описание</span><span class="sxs-lookup"><span data-stu-id="34ffd-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34ffd-136">\<smtp> Элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="34ffd-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="34ffd-137">Настраивает опции отправки почты Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="34ffd-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34ffd-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="34ffd-138">Remarks</span></span>  
 <span data-ttu-id="34ffd-139">Некоторые серверы SMTP требуют, чтобы вы удостоверяли подлинность сервера перед использованием.</span><span class="sxs-lookup"><span data-stu-id="34ffd-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="34ffd-140">Если вы хотите проверить подлинность с помощью учетных данных сети по умолчанию на хосте, установите `defaultCredentials` атрибут. `true`</span><span class="sxs-lookup"><span data-stu-id="34ffd-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="34ffd-141">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> может быть использовано для `defaultCredentials` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="34ffd-142">Вы также можете использовать базовую аутентификацию (имя пользователя и пароль) для проверки подлинности сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="34ffd-143">Чтобы использовать эту опцию, необходимо указать действительное имя пользователя и пароль для указанного сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34ffd-144">Базовая аутентификация отправляет и `userName` `password` значения на сервер незашифрованным.</span><span class="sxs-lookup"><span data-stu-id="34ffd-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="34ffd-145">Любой, кто следит за сетевым трафиком, может просматривать ваши учетные данные и использовать их для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="34ffd-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="34ffd-146">Следует использовать более безопасный механизм аутентификации, такой как Kerberos или NT LAN Manager (NTLM).) Если `defaultCredentials` `true`это так, Kerberos или NTLM будут использоваться, если сервер поддерживает эти протоколы.</span><span class="sxs-lookup"><span data-stu-id="34ffd-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="34ffd-147">Основные параметры аутентификации и учетных данных сети по умолчанию являются взаимоисключающими; если вы `defaultCredentials` `true` установите имя пользователя и пароль, используется учетный сбор сети по умолчанию, а основные данные аутентификации игнорируются.</span><span class="sxs-lookup"><span data-stu-id="34ffd-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="34ffd-148">Для базовой проверки `userName`подлинности, если `password` вы укажете, вы должны также указать для проверки подлинности себя на почтовый сервер.</span><span class="sxs-lookup"><span data-stu-id="34ffd-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="34ffd-149">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> может быть использовано для `userName` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="34ffd-150">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> может быть использовано для `password` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="34ffd-151">Атрибут `password` обычно не вводится в файлы конфигурации по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="34ffd-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="34ffd-152">Атрибут `clientDomain` изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP на сервер SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="34ffd-153">Атрибут `clientDomain` может быть установлен на полностью квалифицированное доменное имя локальной машины, а не на имя локального хозяина, которое используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="34ffd-154">Это обеспечивает более широкое соответствие стандартам протокола SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="34ffd-155">Значение по умолчанию — это локальное имя локального компьютера, отправляя запрос.</span><span class="sxs-lookup"><span data-stu-id="34ffd-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="34ffd-156">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> может быть использовано для `clientDomain` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="34ffd-157">Атрибут `targetName` используется для проверки подлинности при использовании расширенной защиты.</span><span class="sxs-lookup"><span data-stu-id="34ffd-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="34ffd-158">Значение по умолчанию имеет форму "SMTPSVC/host\<>", где \<хост-> является хост-именем почтового сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="34ffd-159">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> может быть использовано для `targetName` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="34ffd-160">Атрибут `enableSsl` определяет, используется ли SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="34ffd-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="34ffd-161">Класс <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> поддерживает только расширение службы SMTP для безопасного SMTP по безопасности транспортного уровня, как это определено в RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="34ffd-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="34ffd-162">В этом режиме сеанс SMTP начинается на незашифрованном канале, затем команда STARTTLS выдается клиентом на сервер для перехода на безопасную связь с помощью SSL.</span><span class="sxs-lookup"><span data-stu-id="34ffd-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="34ffd-163">Дополнительную информацию можно узнать в RFC 3207, опубликованную Целевой группой по интернет-инженерии (IETF).</span><span class="sxs-lookup"><span data-stu-id="34ffd-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="34ffd-164">Альтернативный метод соединения — это место, где сеанс SSL устанавливается заранее перед отправкой команд протокола.</span><span class="sxs-lookup"><span data-stu-id="34ffd-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="34ffd-165">Этот метод соединения иногда называют SMTPS и по умолчанию использует порт 465.</span><span class="sxs-lookup"><span data-stu-id="34ffd-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="34ffd-166">Этот альтернативный метод соединения с использованием SSL в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="34ffd-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="34ffd-167">Свойство <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> может быть использовано для `enableSsl` получения текущей стоимости атрибута из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34ffd-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ffd-168">Пример</span><span class="sxs-lookup"><span data-stu-id="34ffd-168">Example</span></span>  
 <span data-ttu-id="34ffd-169">В следующем примере указаны соответствующие параметры SMTP для отправки электронной почты с использованием учетных данных сети по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34ffd-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="34ffd-170">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="34ffd-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="34ffd-171">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="34ffd-171">Network Settings Schema</span></span>](index.md)
