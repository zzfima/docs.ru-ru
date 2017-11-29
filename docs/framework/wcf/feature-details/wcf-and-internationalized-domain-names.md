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
# <a name="wcf-and-internationalized-domain-names"></a>WCF и международные доменные имена
Добавлена поддержка служб WCF с интернационализированными именами домена (IDN). Интернационализированное имя домена представляет собой имя домена, содержащее символы, не входящие в набор символов ASCII. Данная поддержка включает в себя как возможность размещения службы WCF с именем IDN, так и возможность диалога клиента WCF с веб-службой с именем IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri и IDN  
 У объекта класса <xref:System.Uri> есть два свойства: <xref:System.Uri.Host%2A> и <xref:System.Uri.DnsSafeHost%2A>. Эти свойства содержат значения Unicode или Punycode в зависимости от параметров конфигурации IDN.  
  
 IDN активируется в файле конфигурации приложения с помощью следующего кода XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<Idn > содержит включенный атрибут, который может быть присвоено одно из следующих значений:  
  
1.  «None»  
  
2.  «AllExceptIntranet»  
  
3.  «Все»  
  
 Если параметру IDN имеет значение «None», преобразование не выполняется, Uri.Host и Uri.DnsSafeHost. Если параметру IDN присвоено uri «Все». Узел остается Юникода и uri. DnsSafeHost преобразуется в Punycode. Если параметру IDN присвоено uri «AllExceptIntranet». DnsSafeHost преобразуется в Punycode для адресов Интернета и остается в формате Юникода для адресов интрасети. Этот параметр важен для верного разрешения имен DNS. Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.  
  
> [!WARNING]
>  Никогда не следует вводить адрес вручную с использованием Punycode. WCF преобразует адрес в соответствии с примененными параметрами конфигурации.  
  
> [!WARNING]
>  При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF-8.  
  
## <a name="see-also"></a>См. также  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)
