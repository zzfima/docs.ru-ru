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
ms.openlocfilehash: ee60b990bc749dbb9c5d0e7426c57e9392ddf9d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920971"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="bad27-102">\<Элемент Network > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bad27-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="bad27-103">Настраивает параметры сети для внешнего SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="bad27-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="bad27-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bad27-104">\<configuration></span></span>  
<span data-ttu-id="bad27-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="bad27-105">\<system.net></span></span>  
<span data-ttu-id="bad27-106">\<Маилсеттингс ></span><span class="sxs-lookup"><span data-stu-id="bad27-106">\<mailSettings></span></span>  
<span data-ttu-id="bad27-107">\<> SMTP</span><span class="sxs-lookup"><span data-stu-id="bad27-107">\<smtp></span></span>  
<span data-ttu-id="bad27-108">\<Сетевые ></span><span class="sxs-lookup"><span data-stu-id="bad27-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad27-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bad27-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bad27-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bad27-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bad27-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bad27-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bad27-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bad27-112">Attributes</span></span>  
  
|<span data-ttu-id="bad27-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bad27-113">Attribute</span></span>|<span data-ttu-id="bad27-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bad27-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="bad27-115">Указывает доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="bad27-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="bad27-116">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="bad27-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="bad27-117">Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="bad27-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bad27-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="bad27-119">Указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="bad27-120">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bad27-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="bad27-121">Указывает имя узла почтового SMTP-сервера, используемого для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="bad27-122">У этого атрибута нет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="bad27-123">Указывает пароль, используемый для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="bad27-124">У этого атрибута нет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="bad27-125">Указывает номер порта, используемый для подключения к почтовому SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="bad27-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="bad27-126">Значение по умолчанию — 25.</span><span class="sxs-lookup"><span data-stu-id="bad27-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="bad27-127">Указывает имя поставщика услуг (SPN), используемое для проверки подлинности при использовании расширенной защиты для транзакций SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="bad27-128">У этого атрибута нет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="bad27-129">Указывает имя пользователя, используемое для проверки подлинности на почтовом сервере SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="bad27-130">У этого атрибута нет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bad27-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bad27-131">Child Elements</span></span>  
 <span data-ttu-id="bad27-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="bad27-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bad27-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bad27-133">Parent Elements</span></span>  
  
|<span data-ttu-id="bad27-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="bad27-134">Element</span></span>|<span data-ttu-id="bad27-135">Описание</span><span class="sxs-lookup"><span data-stu-id="bad27-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bad27-136">\<Элемент > SMTP (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bad27-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="bad27-137">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bad27-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="bad27-138">Remarks</span></span>  
 <span data-ttu-id="bad27-139">Некоторые SMTP-серверы должны пройти проверку подлинности на сервере перед использованием.</span><span class="sxs-lookup"><span data-stu-id="bad27-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="bad27-140">Если вы хотите пройти проверку подлинности самостоятельно, используя сетевые учетные данные по умолчанию на `true`узле, задайте `defaultCredentials` для атрибута значение.</span><span class="sxs-lookup"><span data-stu-id="bad27-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="bad27-141">Свойство можно использовать для получения текущего значения `defaultCredentials` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="bad27-142">Для проверки подлинности на SMTP-сервере также можно использовать обычную проверку подлинности (имя пользователя и пароль).</span><span class="sxs-lookup"><span data-stu-id="bad27-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="bad27-143">Чтобы использовать этот параметр, необходимо указать допустимое имя пользователя и пароль для указанного SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="bad27-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bad27-144">Обычная проверка подлинности `password` отправляет `userName` значения и на сервер в незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="bad27-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="bad27-145">Любой пользователь, отслеживающий сетевой трафик, может просматривать ваши учетные данные и использовать их для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="bad27-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="bad27-146">Рекомендуется использовать более безопасный механизм проверки подлинности, например Kerberos или NT LAN Manager (NTLM). Если `defaultCredentials` имеет `true`значение, то используется протокол Kerberos или NTLM, если сервер поддерживает эти протоколы.</span><span class="sxs-lookup"><span data-stu-id="bad27-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="bad27-147">Параметры обычной проверки подлинности и сетевых учетных данных по умолчанию являются взаимоисключающими. Если задано `defaultCredentials` значение `true` и указано имя пользователя и пароль, используются учетные данные сети по умолчанию, а основные данные проверки подлинности игнорируются.</span><span class="sxs-lookup"><span data-stu-id="bad27-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="bad27-148">При обычной проверке подлинности при `userName`указании необходимо также `password` указать для проверки подлинности на почтовом сервере.</span><span class="sxs-lookup"><span data-stu-id="bad27-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="bad27-149">Свойство можно использовать для получения текущего значения `userName` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="bad27-150">Свойство можно использовать для получения текущего значения `password` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="bad27-151">В целях безопасности атрибут обычно не указывается в файлах конфигурации. `password`</span><span class="sxs-lookup"><span data-stu-id="bad27-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="bad27-152">`clientDomain` Атрибут изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP, на SMTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="bad27-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="bad27-153">Для `clientDomain` атрибута можно задать полное доменное имя локального компьютера, а не имя localhost, используемое по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="bad27-154">Это обеспечивает более высокий уровень соответствия стандартам протокола SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="bad27-155">Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.</span><span class="sxs-lookup"><span data-stu-id="bad27-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="bad27-156">Свойство можно использовать для получения текущего значения `clientDomain` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="bad27-157">`targetName` Атрибут используется для проверки подлинности при использовании расширенной защиты.</span><span class="sxs-lookup"><span data-stu-id="bad27-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="bad27-158">Значение по умолчанию — в формате "SMTPSVC/\<Host >", \<где узел > является именем узла почтового SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="bad27-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="bad27-159">Свойство можно использовать для получения текущего значения `targetName` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="bad27-160">Атрибут `enableSsl` указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP.</span><span class="sxs-lookup"><span data-stu-id="bad27-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="bad27-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Класс поддерживает только расширение службы SMTP для защиты SMTP по протоколу TLS, как определено в RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="bad27-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="bad27-162">В этом режиме сеанс SMTP начинается на незашифрованном канале, после чего клиент отправляет на сервер команду STARTTLS, чтобы переключиться на безопасное взаимодействие с помощью SSL.</span><span class="sxs-lookup"><span data-stu-id="bad27-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="bad27-163">Дополнительные сведения см. в RFC 3207, опубликованных с помощью IETF.</span><span class="sxs-lookup"><span data-stu-id="bad27-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="bad27-164">Альтернативный способ подключения заключается в том, где сеанс SSL устанавливается перед отправкой любых команд протокола.</span><span class="sxs-lookup"><span data-stu-id="bad27-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="bad27-165">Этот метод подключения иногда называют SMTP и по умолчанию использует порт 465.</span><span class="sxs-lookup"><span data-stu-id="bad27-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="bad27-166">Этот альтернативный метод подключения, использующий SSL, в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bad27-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="bad27-167">Свойство можно использовать для получения текущего значения `enableSsl` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bad27-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bad27-168">Пример</span><span class="sxs-lookup"><span data-stu-id="bad27-168">Example</span></span>  
 <span data-ttu-id="bad27-169">В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bad27-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bad27-170">См. также</span><span class="sxs-lookup"><span data-stu-id="bad27-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="bad27-171">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="bad27-171">Network Settings Schema</span></span>](index.md)
