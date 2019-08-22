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
ms.openlocfilehash: 40d89f7bd7a1f4a38a1c4030a86405e09c497899
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659311"
---
# <a name="network-element-network-settings"></a>\<Элемент Network > (параметры сети)
Настраивает параметры сети для внешнего SMTP-сервера.  
  
 \<configuration>  
\<> System. NET  
\<Маилсеттингс >  
\<> SMTP  
\<Сетевые >  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`clientDomain`|Указывает доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому SMTP-серверу. Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос.|  
|`defaultCredentials`|Указывает, следует ли использовать учетные данные пользователя по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP. Значение по умолчанию — `false`.|  
|`enableSsl`|Указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP. Значение по умолчанию — `false`.|  
|`host`|Указывает имя узла почтового SMTP-сервера, используемого для транзакций SMTP. У этого атрибута нет значения по умолчанию.|  
|`password`|Указывает пароль, используемый для проверки подлинности на почтовом сервере SMTP. У этого атрибута нет значения по умолчанию.|  
|`port`|Указывает номер порта, используемый для подключения к почтовому SMTP-серверу. Значение по умолчанию — 25.|  
|`targetName`|Указывает имя поставщика услуг (SPN), используемое для проверки подлинности при использовании расширенной защиты для транзакций SMTP. У этого атрибута нет значения по умолчанию.|  
|`userName`|Указывает имя пользователя, используемое для проверки подлинности на почтовом сервере SMTP. У этого атрибута нет значения по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Элемент > SMTP (параметры сети)](smtp-element-network-settings.md)|Настраивает параметры отправки почты по протоколу SMTP.|  
  
## <a name="remarks"></a>Примечания  
 Некоторые SMTP-серверы должны пройти проверку подлинности на сервере перед использованием. Если вы хотите пройти проверку подлинности самостоятельно, используя сетевые учетные данные по умолчанию на `true`узле, задайте `defaultCredentials` для атрибута значение. Свойство можно использовать для получения текущего значения `defaultCredentials` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>  
  
 Для проверки подлинности на SMTP-сервере также можно использовать обычную проверку подлинности (имя пользователя и пароль). Чтобы использовать этот параметр, необходимо указать допустимое имя пользователя и пароль для указанного SMTP-сервера.  
  
> [!NOTE]
>  Обычная проверка подлинности `password` отправляет `userName` значения и на сервер в незашифрованном виде. Любой пользователь, отслеживающий сетевой трафик, может просматривать ваши учетные данные и использовать их для подключения к серверу. Рекомендуется использовать более безопасный механизм проверки подлинности, например Kerberos или NT LAN Manager (NTLM). Если `defaultCredentials` имеет `true`значение, то используется протокол Kerberos или NTLM, если сервер поддерживает эти протоколы.  
  
 Параметры обычной проверки подлинности и сетевых учетных данных по умолчанию являются взаимоисключающими. Если задано `defaultCredentials` значение `true` и указано имя пользователя и пароль, используются учетные данные сети по умолчанию, а основные данные проверки подлинности игнорируются.  
  
 При обычной проверке подлинности при `userName`указании необходимо также `password` указать для проверки подлинности на почтовом сервере.  
  
 Свойство можно использовать для получения текущего значения `userName` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Свойство можно использовать для получения текущего значения `password` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> В целях безопасности атрибут обычно не указывается в файлах конфигурации. `password`  
  
 `clientDomain` Атрибут изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP, на SMTP-сервер. Для `clientDomain` атрибута можно задать полное доменное имя локального компьютера, а не имя localhost, используемое по умолчанию. Это обеспечивает более высокий уровень соответствия стандартам протокола SMTP. Значение по умолчанию — имя localhost локального компьютера, отправляющего запрос. Свойство можно использовать для получения текущего значения `clientDomain` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>  
  
 `targetName` Атрибут используется для проверки подлинности при использовании расширенной защиты. Значение по умолчанию — в формате "SMTPSVC/\<Host >", \<где узел > является именем узла почтового SMTP-сервера. Свойство можно использовать для получения текущего значения `targetName` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>  
  
 Атрибут `enableSsl` указывает, используется ли протокол SSL для доступа к почтовому серверу SMTP. <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Класс поддерживает только расширение службы SMTP для защиты SMTP по протоколу TLS, как определено в RFC 3207. В этом режиме сеанс SMTP начинается на незашифрованном канале, после чего клиент отправляет на сервер команду STARTTLS, чтобы переключиться на безопасное взаимодействие с помощью SSL. Дополнительные сведения см. в RFC 3207, опубликованных с помощью IETF.  
  
 Альтернативный способ подключения заключается в том, где сеанс SSL устанавливается перед отправкой любых команд протокола. Этот метод подключения иногда называют SMTP и по умолчанию использует порт 465. Этот альтернативный метод подключения, использующий SSL, в настоящее время не поддерживается.  
  
 Свойство можно использовать для получения текущего значения `enableSsl` атрибута из применимых файлов конфигурации. <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>Пример  
 В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
