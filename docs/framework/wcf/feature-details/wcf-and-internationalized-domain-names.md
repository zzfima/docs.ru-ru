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
  
2.  Значение «AllExceptIntranet»  
  
3.  «Все»  
  
 Если параметру IDN присвоено «None», преобразование не выполняется, Uri.Host и Uri.DnsSafeHost. Если параметру IDN присвоено «All», uri. Узел остается Юникода и uri. DnsSafeHost преобразуется в Punycode. Если параметру IDN присвоено значение «AllExceptIntranet», uri. DnsSafeHost преобразуется в Punycode для адресов Интернета и остается в формате Юникода для адресов интрасети. Этот параметр важен для верного разрешения имен DNS. Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.  
  
> [!WARNING]
>  Никогда не следует вводить адрес вручную с использованием Punycode. WCF преобразует адрес в соответствии с примененными параметрами конфигурации.  
  
> [!WARNING]
>  При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF-8.  
  
## <a name="see-also"></a>См. также  
 [System.Uri](https://msdn.microsoft.com/library/system.uri.aspx)
