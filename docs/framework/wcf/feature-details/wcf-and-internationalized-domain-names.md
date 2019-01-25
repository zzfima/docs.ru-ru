---
title: WCF и международные доменные имена
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 83c6f3c2afec0f2b6b8fccca4bd8252e9ab35400
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571591"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="7c29d-102">WCF и международные доменные имена</span><span class="sxs-lookup"><span data-stu-id="7c29d-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="7c29d-103">Добавлена поддержка служб WCF с интернационализированными именами домена (IDN).</span><span class="sxs-lookup"><span data-stu-id="7c29d-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="7c29d-104">Интернационализированное имя домена представляет собой имя домена, содержащее символы, не входящие в набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="7c29d-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="7c29d-105">Данная поддержка включает в себя как возможность размещения службы WCF с именем IDN, так и возможность диалога клиента WCF с веб-службой с именем IDN.</span><span class="sxs-lookup"><span data-stu-id="7c29d-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="7c29d-106">System.Uri и IDN</span><span class="sxs-lookup"><span data-stu-id="7c29d-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="7c29d-107">У объекта класса <xref:System.Uri> есть два свойства: <xref:System.Uri.Host%2A> и <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c29d-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="7c29d-108">Эти свойства содержат значения Unicode или Punycode в зависимости от параметров конфигурации IDN.</span><span class="sxs-lookup"><span data-stu-id="7c29d-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="7c29d-109">IDN активируется в файле конфигурации приложения с помощью следующего кода XML</span><span class="sxs-lookup"><span data-stu-id="7c29d-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="7c29d-110">\<Idn > содержит включенный атрибут, который может быть присвоено одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="7c29d-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="7c29d-111">«None»</span><span class="sxs-lookup"><span data-stu-id="7c29d-111">"None"</span></span>  
  
2.  <span data-ttu-id="7c29d-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="7c29d-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="7c29d-113">«Все»</span><span class="sxs-lookup"><span data-stu-id="7c29d-113">"All"</span></span>  
  
 <span data-ttu-id="7c29d-114">Если параметру IDN присвоено «None», преобразование не выполняется, Uri.Host и Uri.DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="7c29d-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="7c29d-115">Если параметру IDN присвоено «All», uri. Узел остается Юникода и uri. DnsSafeHost преобразуется в Punycode.</span><span class="sxs-lookup"><span data-stu-id="7c29d-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="7c29d-116">Если параметру IDN присвоено значение «AllExceptIntranet», uri. DnsSafeHost преобразуется в Punycode для адресов Интернета и остается в формате Юникода для адресов интрасети.</span><span class="sxs-lookup"><span data-stu-id="7c29d-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="7c29d-117">Этот параметр важен для верного разрешения имен DNS.</span><span class="sxs-lookup"><span data-stu-id="7c29d-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="7c29d-118">Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="7c29d-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7c29d-119">Никогда не следует вводить адрес вручную с использованием Punycode.</span><span class="sxs-lookup"><span data-stu-id="7c29d-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="7c29d-120">WCF преобразует адрес в соответствии с примененными параметрами конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7c29d-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7c29d-121">При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="7c29d-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c29d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7c29d-122">See also</span></span>
- <xref:System.Uri?displayProperty=nameWithType>
