---
title: WCF и международные доменные имена
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 8431f5d47aa32d1c928190abdd3079831ca48618
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208430"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="0b7ed-102">WCF и международные доменные имена</span><span class="sxs-lookup"><span data-stu-id="0b7ed-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="0b7ed-103">Добавлена поддержка служб WCF с интернационализированными именами домена (IDN).</span><span class="sxs-lookup"><span data-stu-id="0b7ed-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="0b7ed-104">Интернационализированное имя домена представляет собой имя домена, содержащее символы, не входящие в набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="0b7ed-105">Данная поддержка включает в себя как возможность размещения службы WCF с именем IDN, так и возможность диалога клиента WCF с веб-службой с именем IDN.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="0b7ed-106">System.Uri и IDN</span><span class="sxs-lookup"><span data-stu-id="0b7ed-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="0b7ed-107">У объекта класса <xref:System.Uri> есть два свойства: <xref:System.Uri.Host%2A> и <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="0b7ed-108">Эти свойства содержат значения Unicode или Punycode в зависимости от параметров конфигурации IDN.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="0b7ed-109">IDN активируется в файле конфигурации приложения с помощью следующего кода XML</span><span class="sxs-lookup"><span data-stu-id="0b7ed-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="0b7ed-110">\<Idn > содержит включенный атрибут, который может быть присвоено одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0b7ed-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="0b7ed-111">«None»</span><span class="sxs-lookup"><span data-stu-id="0b7ed-111">"None"</span></span>  
  
2.  <span data-ttu-id="0b7ed-112">Значение «AllExceptIntranet»</span><span class="sxs-lookup"><span data-stu-id="0b7ed-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="0b7ed-113">«Все»</span><span class="sxs-lookup"><span data-stu-id="0b7ed-113">"All"</span></span>  
  
 <span data-ttu-id="0b7ed-114">Если параметру IDN присвоено «None», преобразование не выполняется, Uri.Host и Uri.DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="0b7ed-115">Если параметру IDN присвоено «All», uri. Узел остается Юникода и uri. DnsSafeHost преобразуется в Punycode.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="0b7ed-116">Если параметру IDN присвоено значение «AllExceptIntranet», uri. DnsSafeHost преобразуется в Punycode для адресов Интернета и остается в формате Юникода для адресов интрасети.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="0b7ed-117">Этот параметр важен для верного разрешения имен DNS.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="0b7ed-118">Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0b7ed-119">Никогда не следует вводить адрес вручную с использованием Punycode.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="0b7ed-120">WCF преобразует адрес в соответствии с примененными параметрами конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0b7ed-121">При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0b7ed-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7ed-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0b7ed-122">See Also</span></span>  
 [<span data-ttu-id="0b7ed-123">System.Uri</span><span class="sxs-lookup"><span data-stu-id="0b7ed-123">System.Uri</span></span>](https://msdn.microsoft.com/library/system.uri.aspx)
