---
title: "WCF и международные доменные имена | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF и международные доменные имена
Добавлена поддержка служб WCF с интернационализированными именами домена \(IDN\).  Интернационализированное имя домена представляет собой имя домена, содержащее символы, не входящие в набор символов ASCII.  Данная поддержка включает в себя как возможность размещения службы WCF с именем IDN, так и возможность диалога клиента WCF с веб\-службой с именем IDN.  
  
## System.Uri и IDN  
 У объекта класса <xref:System.Uri> есть два свойства: <xref:System.Uri.Host%2A> и <xref:System.Uri.DnsSafeHost%2A>.  Эти свойства содержат значения Unicode или Punycode в зависимости от параметров конфигурации IDN.  
  
 IDN активируется в файле конфигурации приложения с помощью следующего кода XML  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
  
```  
  
 Элемент \<idn\> содержит включенный атрибут, который может принимать одно из следующих значений:  
  
1.  None  
  
2.  AllExceptIntranet  
  
3.  All  
  
 Если параметру IDN присвоено значение None, Uri.Host и Uri.DnsSafeHost не выполняют никаких преобразований.  Если параметру IDN присвоено значение All, uri.Host остается в формате Юникода, а uri.DnsSafeHost преобразуется в Punycode.  Если параметру IDN присвоено значение AllExceptIntranet, uri.DnsSafeHost преобразуется в Punycode для внешних адресов \(Интернет\) и остается в формате Юникода для внутренних адресов \(интрасеть\).  Этот параметр важен для верного разрешения имен DNS.  Обратите внимание, что он не требует настройки в Windows 8 и более поздних версиях.  
  
> [!WARNING]
>  Никогда не следует вводить адрес вручную с использованием Punycode.  WCF преобразует адрес в соответствии с примененными параметрами конфигурации.  
  
> [!WARNING]
>  При добавлении в applicationHost.exe.config символов Юникода сохраните файл в кодировке UTF\-8.  
  
## См. также  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)