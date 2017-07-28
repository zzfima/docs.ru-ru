---
title: "NetworkInformation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Сеть"
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# NetworkInformation
Пространство имен <xref:System.Net.NetworkInformation> позволяет собирать сведения о событиях, изменениях, статистики и свойствах сети.  Можно также указать, следует ли удаленный узел доступен с помощью класса <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName>.  
  
## Доступность сети и события  
 Класс <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> позволяет определить, были ли изменены адрес или доступности сети.  Для использования этого класса, создайте обработчик событий для обработки и свяжите его с <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> или <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.  Дополнительные сведения см. в разделе [Практическое руководство. Определение доступности сети и изменений адреса](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## Статистика и свойства сети  
 Можно собрать статистику и свойства сети на интерфейс или уровне протокола.  <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> и классы <xref:System.Net.NetworkInformation.PhysicalAddress> предоставляют сведения о конкретном сетевом интерфейсе, пока <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> и классы <xref:System.Net.NetworkInformation.UdpStatistics> предоставляют сведения о пакетах уровня 3 и 4 уровня.  Дополнительные сведения см. в разделе [Практическое руководство. Получение информации об интерфейсах и протоколах](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## Укажите если удаленный узел доступен  
 Можно использовать класс <xref:System.Net.NetworkInformation.Ping> для определения, может ли удаленный узел поиск в сети и доступен.  Дополнительные сведения см. в разделе [Практическое руководство. Проверка связи с узлом](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## См. также  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Образец отдела информационных технологий сети](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [Образец технологии средства NetStat](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [Образец технологии клиента проверки связи](http://go.microsoft.com/fwlink/?LinkID=179565)