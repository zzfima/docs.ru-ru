---
title: "/ baseaddress | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 527a7c348583498f46ee094ef9b9eec9abf1bcd0
ms.lasthandoff: 03/13/2017

---
# <a name="baseaddress"></a>/baseaddress
Задает базовый адрес при создании библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`address`|Обязательный. Базовый адрес библиотеки DLL. Этот адрес должен указан как шестнадцатеричное число.|  
  
## <a name="remarks"></a>Примечания  
 Базовый адрес библиотеки DLL по умолчанию задается [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 Имейте в виду, что младшее слово адреса округляется. Например если будет указано 0x11110001, оно округляется до 0x11110000.  
  
 Для подписывания библиотеки DLL используйте `–R` параметр инструмента строгого именования (Sn.exe).  
  
 Этот параметр учитывается, если целевой объект не является библиотекой DLL.  
  
|Установка/baseaddress в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в **базовый адрес DLL:** поле. **Примечание:** **базовый адрес DLL:** поле доступно только для чтения, если целевым является не DLL.|  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23)
