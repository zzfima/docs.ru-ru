---
title: "Включение и отключение IPv6 | Microsoft Docs"
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
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Включение и отключение IPv6
Для использования протокола IP версии 6, убедитесь, что используется версия операционной системы, которая поддерживает IP версии 6 и убедиться, что операционная система и классы сети настроитьы правильно.  
  
## Этапы конфигурации  
 В следующей таблице перечислены различные конфигурации  
  
|Операционная система IPv6\-enabled?|Сеть classify IPv6\-enabled?|Описание|  
|-----------------------------------------|----------------------------------|--------------|  
|Нет|Нет|Удалось выполнить синтаксический анализ адреса IP версии 6.|  
|Нет|Да|Удалось выполнить синтаксический анализ адреса IP версии 6.|  
|Да|Нет|Удалось выполнить синтаксический анализ адреса IP версии 6 и разрешения адреса IP версии 6 с помощью методов разрешения имен помечен как устаревший.|  
|Да|Да|Удалось выполнить синтаксический анализ и разрешения адреса IP версии 6 с помощью все методы в том числе пометил устаревшими.|  
  
 Помните, что, чтобы включить поддержку IP версии 6 для всех классов в пространстве имен System.Net, необходимо изменить файл конфигурации компьютера или в файле конфигурации приложения.  Файл конфигурации приложения имеет приоритет над файлом конфигурации компьютера.  
  
 Пример, как изменить файл конфигурации компьютера *machine.config*, чтобы включить поддержку протоколы Ipv6 см. в разделе [Практическое руководство. Измените файл конфигурации компьютера, чтобы включить поддержку протоколы Ipv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  Также убедитесь, что включена поддержка IP версии 6 для операционной системы.  
  
 Платформы .NET Framework имеет параметр конфигурации задан в файле конфигурации следующим образом  
  
```  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 Для платформы .NET Framework версии 1.1 и более ранних версий значение параметра конфигурации **ipv6 enabled** определяет, могут ли члены адреса IP версии 6, возвращают класса <xref:System.Net.Dns?displayProperty=fullName>.  
  
 Для платформы .NET Framework версии 2.0 и более поздних, если Windows поддерживает IP версии 6, то члены класса <xref:System.Net.Dns?displayProperty=fullName> \(например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> \) вернет адреса IP версии 6 с одним ограничением.  Устаревшие члены DNS <xref:System.Net.Dns?displayProperty=fullName> \(например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> \) прочитают и распознают значения в файле конфигурации для параметра, включенного протоколы ipv6.  
  
## См. также  
 [Протокол IP версии 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Сокеты](../../../docs/framework/network-programming/sockets.md)   
 [Схема параметров сети](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Элемент \<ipv6\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)