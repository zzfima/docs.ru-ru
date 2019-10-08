---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002385"
---
# <a name="-baseaddress"></a>-baseaddress
Задает базовый адрес по умолчанию при создании библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`address`|Обязательный. Базовый адрес для библиотеки DLL. Этот адрес должен быть указан в виде шестнадцатеричного числа.|  
  
## <a name="remarks"></a>Примечания  
 Базовый адрес по умолчанию для библиотеки DLL задается .NET Framework.  
  
 Имейте в виду, что младшее слово в этом адресе округляется. Например, если указать 0x11110001, он округляется до 0x11110000.  
  
 Чтобы завершить процесс подписывания библиотеки DLL, используйте параметр `–R` средства строгого именования (Sn. exe).  
  
 Этот параметр не учитывается, если целевой объект не является библиотекой DLL.  
  
|Установка параметра-BaseAddress в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в поле **базовый адрес DLL:** . **Примечание.**      **Базовый адрес DLL:** Box доступен только для чтения, если целевой объект не является библиотекой DLL.|  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))
