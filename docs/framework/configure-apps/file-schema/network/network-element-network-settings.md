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
# <a name="network-element-network-settings"></a>\<сетевой элемент> (Настройки сети)
Настраивает параметры сети для внешнего сервера Simple Mail Transport Protocol (SMTP).  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сети>**

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
  
|attribute|Описание|  
|---------------|-----------------|  
|`clientDomain`|Упогоняет доменное имя клиента для использования в первоначальном запросе протокола SMTP для подключения к почтовому серверу SMTP. Значение по умолчанию — это локальное имя локального компьютера, отправляя запрос.|  
|`defaultCredentials`|Уточняется, следует ли использовать учетные данные пользователей по умолчанию для доступа к почтовому серверу SMTP для транзакций SMTP. Значение по умолчанию — `false`.|  
|`enableSsl`|Уточняется, используется ли SSL для доступа к почтовому серверу SMTP. Значение по умолчанию — `false`.|  
|`host`|Упогоняет имя почтового сервера SMTP для использования для транзакций SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`password`|Упогоняет пароль для использования для проверки подлинности на почтовом сервере SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`port`|Определяет номер порта для подключения к почтовому серверу SMTP. По умолчанию используется значение 25.|  
|`targetName`|Учреждать имя поставщика услуг (SPN) для использования для проверки подлинности при использовании расширенной защиты для транзакций SMTP. Этот атрибут не имеет значения по умолчанию.|  
|`userName`|Упогоняет имя пользователя для использования для проверки подлинности на почтовом сервере SMTP. Этот атрибут не имеет значения по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<smtp> Элемент (Настройки сети)](smtp-element-network-settings.md)|Настраивает опции отправки почты Simple Mail Transport Protocol (SMTP).|  
  
## <a name="remarks"></a>Remarks  
 Некоторые серверы SMTP требуют, чтобы вы удостоверяли подлинность сервера перед использованием. Если вы хотите проверить подлинность с помощью учетных данных сети по умолчанию на хосте, установите `defaultCredentials` атрибут. `true` Свойство <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> может быть использовано для `defaultCredentials` получения текущей стоимости атрибута из применимых файлов конфигурации.  
  
 Вы также можете использовать базовую аутентификацию (имя пользователя и пароль) для проверки подлинности сервера SMTP. Чтобы использовать эту опцию, необходимо указать действительное имя пользователя и пароль для указанного сервера SMTP.  
  
> [!NOTE]
> Базовая аутентификация отправляет и `userName` `password` значения на сервер незашифрованным. Любой, кто следит за сетевым трафиком, может просматривать ваши учетные данные и использовать их для подключения к серверу. Следует использовать более безопасный механизм аутентификации, такой как Kerberos или NT LAN Manager (NTLM).) Если `defaultCredentials` `true`это так, Kerberos или NTLM будут использоваться, если сервер поддерживает эти протоколы.  
  
 Основные параметры аутентификации и учетных данных сети по умолчанию являются взаимоисключающими; если вы `defaultCredentials` `true` установите имя пользователя и пароль, используется учетный сбор сети по умолчанию, а основные данные аутентификации игнорируются.  
  
 Для базовой проверки `userName`подлинности, если `password` вы укажете, вы должны также указать для проверки подлинности себя на почтовый сервер.  
  
 Свойство <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> может быть использовано для `userName` получения текущей стоимости атрибута из применимых файлов конфигурации. Свойство <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> может быть использовано для `password` получения текущей стоимости атрибута из применимых файлов конфигурации. Атрибут `password` обычно не вводится в файлы конфигурации по соображениям безопасности.  
  
 Атрибут `clientDomain` изменяет доменное имя клиента, используемое в первоначальном запросе протокола SMTP на сервер SMTP. Атрибут `clientDomain` может быть установлен на полностью квалифицированное доменное имя локальной машины, а не на имя локального хозяина, которое используется по умолчанию. Это обеспечивает более широкое соответствие стандартам протокола SMTP. Значение по умолчанию — это локальное имя локального компьютера, отправляя запрос. Свойство <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> может быть использовано для `clientDomain` получения текущей стоимости атрибута из применимых файлов конфигурации.  
  
 Атрибут `targetName` используется для проверки подлинности при использовании расширенной защиты. Значение по умолчанию имеет форму "SMTPSVC/host\<>", где \<хост-> является хост-именем почтового сервера SMTP. Свойство <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> может быть использовано для `targetName` получения текущей стоимости атрибута из применимых файлов конфигурации.  
  
 Атрибут `enableSsl` определяет, используется ли SSL для доступа к почтовому серверу SMTP. Класс <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> поддерживает только расширение службы SMTP для безопасного SMTP по безопасности транспортного уровня, как это определено в RFC 3207. В этом режиме сеанс SMTP начинается на незашифрованном канале, затем команда STARTTLS выдается клиентом на сервер для перехода на безопасную связь с помощью SSL. Дополнительную информацию можно узнать в RFC 3207, опубликованную Целевой группой по интернет-инженерии (IETF).  
  
 Альтернативный метод соединения — это место, где сеанс SSL устанавливается заранее перед отправкой команд протокола. Этот метод соединения иногда называют SMTPS и по умолчанию использует порт 465. Этот альтернативный метод соединения с использованием SSL в настоящее время не поддерживается.  
  
 Свойство <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> может быть использовано для `enableSsl` получения текущей стоимости атрибута из применимых файлов конфигурации.  
  
## <a name="example"></a>Пример  
 В следующем примере указаны соответствующие параметры SMTP для отправки электронной почты с использованием учетных данных сети по умолчанию.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Схема настройки сети](index.md)
