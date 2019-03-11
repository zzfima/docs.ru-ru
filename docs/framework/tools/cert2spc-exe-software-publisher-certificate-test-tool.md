---
title: Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faa8e28297aa96ab199e80b476783295173f51b5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498878"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (средство проверки сертификата издателя программного обеспечения)
Программа для проверки сертификата издателя программного обеспечения служит для создания сертификата издателя программного обеспечения (SPC) из одного или нескольких сертификатов X.509. Программа Cert2spc.exe используется только для тестирования. Действительный сертификат SPC можно получить в центрах сертификации, таких как VeriSign и Thawte. Дополнительные сведения о создании сертификатов X.509 см. в разделе [Makecert.exe (средство создания сертификатов)](/windows/desktop/SecCrypto/makecert).  
  
 Эта программа автоматически устанавливается вместе с Visual Studio. Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7). Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a>Параметры  
  
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
- [Инструменты](../../../docs/framework/tools/index.md)
- [Makecert.exe (средство создания сертификатов)](/windows/desktop/SecCrypto/makecert)
- [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
