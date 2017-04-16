---
title: "Cert2spc.exe (Software Publisher Certificate Test Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "SPC"
  - "Software Publisher Certificate Test tool"
  - "Software Publisher Certificate"
  - "Cert2spc.exe"
  - "certificates, Software Publisher's Certificate"
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Cert2spc.exe (Software Publisher Certificate Test Tool)
Программа для проверки сертификата издателя программного обеспечения служит для создания сертификата издателя программного обеспечения \(SPC\) из одного или нескольких сертификатов X.509.  Программа Cert2spc.exe используется только для тестирования.  Действительный сертификат SPC можно получить в центрах сертификации, таких как VeriSign и Thawte.  Дополнительные сведения о создании сертификатов X.509 см. в разделе [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md).  
  
 Эта программа автоматически устанавливается вместе с Visual Studio.  Программу можно запустить из командной строки разработчика \(или из командной строки Visual Studio в Windows 7\).  Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## Синтаксис  
  
```  
  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### Параметры  
  
|Аргумент|Описание|  
|--------------|--------------|  
|`certN.cer`|Имя сертификата X.509, включаемого в SPC\-файл.  Можно указать несколько имен, разделенных пробелами.|  
|`crlN.crl`|Имя списка отзыва сертификатов для включения в SPC\-файл.  Можно указать несколько имен, разделенных пробелами.|  
|`outputSPCfile.spc`|Имя объекта PKCS \#7, который будет содержать сертификаты X.509.|  
  
|Параметр|Описание|  
|--------------|--------------|  
|**\/?**|Отображает синтаксис команд и параметров программы.|  
  
## Примеры  
 Следующая команда создает SPC\-файл из файла `myCertificate.cer` и помещает его в файл `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 Следующая команда создает SPC\-файл из файлов `oneCertificate.cer` и `twoCertificate.cer` и помещает его в файл `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## См. также  
 [Tools](../../../docs/framework/tools/index.md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md)