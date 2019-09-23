---
title: Включение и отключение IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 66c802dd5feb865faf7469cb7da04fbffcb4a2d6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048562"
---
# <a name="enabling-and-disabling-ipv6"></a>Включение и отключение IPv6
Чтобы использовать протокол IPv6, убедитесь, что он поддерживается вашей версией операционной системы, а также что операционная система и сетевые классы настроены должным образом.  
  
## <a name="configuration-steps"></a>Шаги настройки  
 В следующей таблице перечислены различные конфигурации  
  
|Операционная система поддерживает протокол IPv6?|Сетевые классы поддерживают протокол IPv6?|ОПИСАНИЕ|  
|-------------------------------------|---------------------------------------|-----------------|  
|Нет|Нет|Можно анализировать IPv6-адреса.|  
|Нет|Yes|Можно анализировать IPv6-адреса.|  
|Yes|Нет|Можно анализировать IPv6-адреса и разрешать их, используя методы разрешения имен, не помеченные как устаревшие.|  
|Yes|Yes|Можно анализировать и разрешать IPv6-адреса, используя все методы, в том числе и помеченные как устаревшие.|  
  
 Обратите внимание, что если требуется включить поддержку IPv6 для всех классов в пространстве имен System.Net, необходимо изменить файл конфигурации компьютера или приложения. Файл конфигурации приложения имеет более высокий приоритет, чем файл конфигурации компьютера.  
  
 Пример изменения файла конфигурации компьютера (*machine.config*) для включения поддержки IPv6 см. в разделе [Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md). Также убедитесь, что в операционной системе включена поддержка протокола IPv6.  
  
 В файле конфигурации для платформы .NET Framework параметры установлены следующим образом  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-адреса.  
  
 Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) будут возвращать IPv6-адреса с одним ограничением. Устаревшие члены службы доменных имен <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) считывают и распознают значение из файла конфигурации для параметра ipv6 enabled.  
  
## <a name="see-also"></a>См. также

- [Протокол IP версии 6](internet-protocol-version-6.md)
- [Сокеты](sockets.md)
- [Схема параметров сети](../configure-apps/file-schema/network/index.md)
- [Элемент \<ipv6> (сетевые параметры)](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
