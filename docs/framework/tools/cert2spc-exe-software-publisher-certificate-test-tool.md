---
title: "Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c720da81c63b612201ede5f648f6861470b25bee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)
Программа для проверки сертификата издателя программного обеспечения служит для создания сертификата издателя программного обеспечения (SPC) из одного или нескольких сертификатов X.509. Программа Cert2spc.exe используется только для тестирования. Действительный сертификат SPC можно получить в центрах сертификации, таких как VeriSign и Thawte. Дополнительные сведения о создании сертификатов X.509 см. в разделе [Makecert.exe (средство создания сертификатов)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).  
  
 Это средство автоматически устанавливается с Visual Studio. Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7). Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Аргумент|Описание|  
|--------------|-----------------|  
|`certN.cer`|Имя сертификата X.509, включаемого в SPC-файл. Можно указать несколько имен, разделенных пробелами.|  
|`crlN.crl`|Имя списка отзыва сертификатов для включения в SPC-файл. Можно указать несколько имен, разделенных пробелами.|  
|`outputSPCfile.spc`|Имя объекта PKCS #7, который будет содержать сертификаты X.509.|  
  
|Параметр|Описание|  
|------------|-----------------|  
|**/?**|Отображает синтаксис команд и параметров программы.|  
  
## <a name="examples"></a>Примеры  
 Следующая команда создает SPC-файл из файла `myCertificate.cer` и помещает его в файл `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 Следующая команда создает SPC-файл из файлов `oneCertificate.cer` и `twoCertificate.cer` и помещает его в файл `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a>См. также  
 [Инструменты](../../../docs/framework/tools/index.md)  
 [Makecert.exe (средство создания сертификатов)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)  
 [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
