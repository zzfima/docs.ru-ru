---
title: '&lt;servicePointManager&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5903174f125938923a63fc031421a8d5a020e56d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt; элемент (параметры сети)
Настраивает подключения к сетевым ресурсам.  
  
 \<configuration>  
\<System.NET >  
\<Параметры >  
\<servicePointManager >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`checkCertificateName`|Указывает, должен ли система проверить соответствие имени узла сервера перед использованием сертификата имя сертификата. Значение по умолчанию — `true`.|  
|`checkCertificateRevocationList`|Указывает, должна ли система проверять был отозван ли сертификат, перед использованием сертификата. Значение по умолчанию — `false`.|  
|`dnsRefreshTimeout`|Указывает срок службы доменных имен (DNS) разрешений кэшируются в сочетании с параметром циклического перебора DNS, в миллисекундах. По умолчанию установлено значение 120 000 миллисекунд (2 минуты).|  
|`enableDnsRoundRobin`|Указывает имена ли разрешенные DNS-узла с помощью нескольких адресов протокола IP (Internet) возвращаемого все адреса или только первый из них. Значение по умолчанию — `false`.|  
|`encryptionPolicy`|Указывает политики шифрования, примененные к сеанса SSL/TLS на <xref:System.Net.ServicePointManager> экземпляра. Возможные значения равны значениям для <xref:System.Net.Security.EncryptionPolicy> перечисления. Использование <xref:System.Security.Authentication.CipherAlgorithmType.Null> является обязательным, если политика шифрования `NoEncryption`. Значение по умолчанию — `RequireEncryption`.|  
|`expect100Continue`|Указывает ли методам POST ожидать получения `100-continue` ответа от сервера. Значение по умолчанию — `true`.|  
|`useNagleAlgorithm`|Указывает, управляемых диспетчером службы точки подключения использовать алгоритм Nagle. Значение по умолчанию — `true`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
