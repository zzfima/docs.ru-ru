---
title: Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 32aa1c3fa50d5c0486da4ef6799c77ead605b504
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187261"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
В следующем примере кода показано, как изменить файл конфигурации компьютера, *machine.config*, чтобы включить поддержку IPv6. Файл *machine.config* находится в папке *%Windir%\Microsoft.NET\Framework* в каталоге установки ОС Windows. В папках *%Windir%\Microsoft.NET\Framework* находятся отдельные файлы *machine.config* для каждой версии .NET Framework, установленной на компьютере (например, *C: \WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.  
  
 Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-адреса.  
  
 Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то все члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) будут возвращать адреса IPv6 с одним ограничением. Устаревшие члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) считают и распознают значение из файла конфигурации.  
  
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
