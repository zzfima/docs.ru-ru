---
title: Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: af6eb8a334108c988967a555024b524e27d40f58
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959081"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="efcec-102">Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6</span><span class="sxs-lookup"><span data-stu-id="efcec-102">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="efcec-103">В следующем примере кода показано, как изменить файл конфигурации компьютера, *machine.config*, чтобы включить поддержку IPv6.</span><span class="sxs-lookup"><span data-stu-id="efcec-103">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="efcec-104">Файл *machine.config* находится в папке *%Windir%\Microsoft.NET\Framework* в каталоге установки ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="efcec-104">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="efcec-105">В папках *%Windir%\Microsoft.NET\Framework* находятся отдельные файлы *machine.config* для каждой версии .NET Framework, установленной на компьютере (например, *C: \WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="efcec-105">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="efcec-106">Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="efcec-106">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="efcec-107">Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="efcec-107">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="efcec-108">Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то все члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) будут возвращать адреса IPv6 с одним ограничением.</span><span class="sxs-lookup"><span data-stu-id="efcec-108">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="efcec-109">Устаревшие члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) считают и распознают значение из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="efcec-109">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efcec-110">Для .NET Framework версии 2.0 и более поздней версии протокол IPv6 включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efcec-110">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="efcec-111">Для .NET Framework версии 1.1 и более ранней версии протокол IPv6 отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efcec-111">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efcec-112">Пример</span><span class="sxs-lookup"><span data-stu-id="efcec-112">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="efcec-113">См. также</span><span class="sxs-lookup"><span data-stu-id="efcec-113">See also</span></span>

- [<span data-ttu-id="efcec-114">Адресация IPv6</span><span class="sxs-lookup"><span data-stu-id="efcec-114">IPv6 Addressing</span></span>](../../../docs/framework/network-programming/ipv6-addressing.md)
- [<span data-ttu-id="efcec-115">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="efcec-115">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="efcec-116">Элемент \<ipv6> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="efcec-116">\<ipv6> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
