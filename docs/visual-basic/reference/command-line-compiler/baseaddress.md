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
ms.openlocfilehash: 0fecc8e890f44512fe4ac2058f26fe54db7570a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588617"
---
# <a name="-baseaddress"></a>-baseaddress
Задает базовый адрес по умолчанию при создании библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`address`|Обязательный. Базовый адрес для библиотеки DLL. Необходимо указать этот адрес в шестнадцатеричном формате.|  
  
## <a name="remarks"></a>Примечания  
 Базовый адрес по умолчанию для библиотеки DLL задается [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 Имейте в виду, что младшее слово этого адреса округляется. Например задать значение 0x11110001 округляется до 0x11110000.  
  
 Чтобы завершить процесс подписи для библиотеки DLL, используйте `–R` средства строгих имен (Sn.exe).  
  
 Этот параметр учитывается, если целевой объект не представляет собой библиотеку DLL.  
  
|Чтобы задать - baseaddress в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в **базовый адрес DLL:** поле. **Примечание.**      **Базовый адрес DLL:** поле только для чтения, если целевой объект представляет собой библиотеку DLL.|  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))
