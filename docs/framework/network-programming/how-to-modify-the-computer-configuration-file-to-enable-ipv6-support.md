---
title: "Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6a23a2690b0df30eaa815d0b321200af3a3403e5
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
В следующем примере кода показано, как изменить файл конфигурации компьютера, *machine.config*, чтобы включить поддержку IPv6. Файл *machine.config* находится в папке *%Windir%\Microsoft.NET\Framework* в каталоге установки ОС Windows. В папках *%Windir%\Microsoft.NET\Framework* находятся отдельные файлы *machine.config* для каждой версии .NET Framework, установленной на компьютере (например, *C: \WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.  
  
 Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=fullName> IPv6-адреса.  
  
 Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то все члены класса <xref:System.Net.Dns?displayProperty=fullName> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName>) будут возвращать адреса IPv6 с одним ограничением. Устаревшие члены класса <xref:System.Net.Dns?displayProperty=fullName> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName>) считают и распознают значение из файла конфигурации.  
  
> [!NOTE]
>  Для .NET Framework версии 2.0 и более поздней версии протокол IPv6 включен по умолчанию. Для .NET Framework версии 1.1 и более ранней версии протокол IPv6 отключен по умолчанию.  
  
## <a name="example"></a>Пример  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 [Адресация IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [Схема параметров сети](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Элемент \<ipv6> (сетевые параметры)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)

