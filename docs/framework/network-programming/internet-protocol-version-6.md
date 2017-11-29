---
title: "протокол IP версии 6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e8ac63cae9d70f0249533848fa472da77f04b807
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="internet-protocol-version-6"></a>протокол IP версии 6
Протокол IP версии 6 (IPv6) — это новый набор стандартных протоколов для сетевого уровня Интернета. IPv6 позволяет устранить множество проблем текущей версии набора интернет-протоколов (известного как IPv4), связанных с нехваткой адресов, безопасностью, автоматической настройкой, расширяемостью и т. д. IPv6 расширяет возможности Интернета для активации новых видов приложений, включая приложения для одноранговой сети и мобильных устройств. Ниже приведены основные проблемы текущего протокола IPv4.  
  
-   Быстрое исчерпание диапазона адресов.  
  
     Это привело к использованию трансляторов сетевых адресов (NAT), которые сопоставляют несколько частных адресов с одним общедоступным IP-адресом. Основными проблемами, создаваемыми этим механизмом, являются затраты на обработку и отсутствие сквозной связи.  
  
-   Отсутствие поддержки иерархии.  
  
     Из-за своей изначально предопределенной организации классов в IPv4 отсутствует настоящая иерархическая поддержка. Невозможно структурировать IP-адреса таким образом, который действительно сопоставляет топологию сети. Этот ключевой недостаток приводит к необходимости использования больших таблиц маршрутизации для доставки пакетов IPv4 в любое место в Интернете.  
  
-   Сложная конфигурация сети.  
  
     При использовании протокола IPv4 адреса должны назначаться статически или с помощью протокола конфигурации, например DHCP. В идеальном случае узлам не придется зависеть от администрирования инфраструктуры DHCP. Вместо этого они смогут выполнять самостоятельную настройку с учетом сегмента сети, в котором они расположены.  
  
-   Отсутствие встроенной проверки подлинности и конфиденциальности.  
  
     Для IPv4 не требуется поддержка какого-либо механизма, обеспечивающего проверку подлинности или шифрование передаваемых данных. Этот момент меняется при использовании IPv6. IPSec является требованием поддержки IPv6.  
  
 Новый набор протоколов должен удовлетворять следующим базовым требованиям:  
  
-   Широкомасштабная маршрутизация и адресация с низкими издержками.  
  
-   Автоматическая настройка для различных ситуаций подключения.  
  
-   Встроенная проверка подлинности и конфиденциальность.  
  
 Дополнительные сведения см. в разделах [Адресация IPv6](../../../docs/framework/network-programming/ipv6-addressing.md), [Маршрутизация IPv6](../../../docs/framework/network-programming/ipv6-routing.md), [Автоматическая настройка IPv6](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Включение и отключение IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) и [Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## <a name="references"></a>Ссылки  
 Ниже перечислен ряд документов RFC, которые можно найти на сайте Internet Engineering Task Force ([http://www.ietf.org](http://www.ietf.org/)):  
  
-   RFC 1287, Towards the Future Internet Architecture.  
  
-   RFC 1454, Comparison of Proposals for Next Version of IP.  
  
-   RFC 2373, IP Version 6 Addressing Architecture.  
  
-   RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.  
  
 Сведения, относящиеся к IPv6, можно также найти в [разделе о IPv6 на сайте Technet](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## <a name="see-also"></a>См. также  
 [Пример сокетов IPv6](http://go.microsoft.com/fwlink/?LinkID=179568)  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Сокеты](../../../docs/framework/network-programming/sockets.md)
