---
title: "Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6 | Microsoft Docs"
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
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
Показать пример кода ниже как изменить файл конфигурации компьютера *machine.config*, чтобы включить поддержку IP версии 6.  Файл *machine.config* хранится в папке *%Windir%\\Microsoft.NET\\Framework* в каталоге, где была установлена Windows.  Отдельный файл *machine.config* в папках в области *%Windir%\\Microsoft.NET\\Framework* для каждой версии платформы .NET Framework, установленного на компьютере \(например, *C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config*\).  
  
 Эти параметры также можно сделать в файле конфигурации приложения, которое имеет приоритет над файлом конфигурации компьютера.  
  
 Для платформы .NET Framework версии 1.1 и более ранних версий значение параметра конфигурации **ipv6 enabled** определяет, могут ли члены адреса IP версии 6, возвращают класса <xref:System.Net.Dns?displayProperty=fullName>.  
  
 Для платформы .NET Framework версии 2.0 и более поздних, если Windows поддерживает IP версии 6, то всех членов класса <xref:System.Net.Dns?displayProperty=fullName> \(например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> \) вернет адреса IP версии 6 с одним ограничением.  Устаревшие члены класса <xref:System.Net.Dns?displayProperty=fullName> \(например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> \) прочитают и распознают значения в файле конфигурации.  
  
> [!NOTE]
>  Для платформы .NET Framework версии 2.0 и более поздней версии, IP версии 6 включена по умолчанию.  Для платформы .NET Framework версии 1.1 и более ранних версий IP версии 6, отключенные по умолчанию.  
  
## Пример  
  
```  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## См. также  
 [Адресация IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [Схема параметров сети](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Элемент \<ipv6\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)