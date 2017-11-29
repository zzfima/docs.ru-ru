---
title: "WCF и международные доменные имена"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab9346e7826fcef5151ef976b6ca7f25120fa5a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="0d93e-102">WCF и международные доменные имена</span><span class="sxs-lookup"><span data-stu-id="0d93e-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="0d93e-103">Добавлена поддержка служб WCF с интернационализированными именами домена (IDN).</span><span class="sxs-lookup"><span data-stu-id="0d93e-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="0d93e-104">Интернационализированное имя домена представляет собой имя домена, содержащее символы, не входящие в набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="0d93e-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="0d93e-105">Данная поддержка включает в себя как возможность размещения службы WCF с именем IDN, так и возможность диалога клиента WCF с веб-службой с именем IDN.</span><span class="sxs-lookup"><span data-stu-id="0d93e-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="0d93e-106">System.Uri и IDN</span><span class="sxs-lookup"><span data-stu-id="0d93e-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="0d93e-107">У объекта класса <xref:System.Uri> есть два свойства: <xref:System.Uri.Host%2A> и <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d93e-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="0d93e-108">Эти свойства содержат значения Unicode или Punycode в зависимости от параметров конфигурации IDN.</span><span class="sxs-lookup"><span data-stu-id="0d93e-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="0d93e-109">IDN активируется в файле конфигурации приложения с помощью следующего кода XML</span><span class="sxs-lookup"><span data-stu-id="0d93e-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="0d93e-110">\<Idn > содержит включенный атрибут, который может быть присвоено одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0d93e-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="0d93e-111">«None»</span><span class="sxs-lookup"><span data-stu-id="0d93e-111">"None"</span></span>  
  
2.  <span data-ttu-id="0d93e-112">«AllExceptIntranet»</span><span class="sxs-lookup"><span data-stu-id="0d93e-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="0d93e-113">«Все»</span><span class="sxs-lookup"><span data-stu-id="0d93e-113">"All"</span></span>  
  
 <span data-ttu-id="0d93e-114">Если параметру IDN имеет значение «None», преобразование не выполняется, Uri.Host и Uri.DnsSafeHost.</span><span class="sxs-lookup"><span data-stu-id="0d93e-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="0d93e-115">Если параметру IDN присвоено uri «Все». Узел остается Юникода и uri. DnsSafeHost преобразуется в Punycode.</span><span class="sxs-lookup"><span data-stu-id="0d93e-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="0d93e-116">Если параметру IDN присвоено uri «AllExceptIntranet». DnsSafeHost преобразуется в Punycode для адресов Интернета и остается в формате Юникода для адресов интрасети.</span><span class="sxs-lookup"><span data-stu-id="0d93e-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="0d93e-117">Этот параметр важен для верного разрешения имен DNS.</span><span class="sxs-lookup"><span data-stu-id="0d93e-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="0d93e-118">Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="0d93e-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0d93e-119">Никогда не следует вводить адрес вручную с использованием Punycode.</span><span class="sxs-lookup"><span data-stu-id="0d93e-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="0d93e-120">WCF преобразует адрес в соответствии с примененными параметрами конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0d93e-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0d93e-121">При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0d93e-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d93e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0d93e-122">See Also</span></span>  
 [<span data-ttu-id="0d93e-123">System.Uri</span><span class="sxs-lookup"><span data-stu-id="0d93e-123">System.Uri</span></span>](http://msdn.microsoft.com/library/system.uri.aspx)
