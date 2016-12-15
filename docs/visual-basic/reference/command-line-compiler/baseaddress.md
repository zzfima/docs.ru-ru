---
title: "/baseaddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/baseaddress"
  - "baseaddress"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/baseaddress - параметр компилятора [Visual Basic]"
  - "baseaddress - параметр компилятора [Visual Basic]"
  - "-baseaddress - параметр компилятора [Visual Basic]"
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /baseaddress
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает базовый адрес при создании библиотеки DLL.  
  
## Синтаксис  
  
```  
/baseaddress:address  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`address`|Обязательный.  Базовый адрес DLL.  Должен быть указан как шестнадцатеричное число.|  
  
## Заметки  
 Базовый адрес по умолчанию для DLL задается [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 Имейте в виду, что младшее слово адреса округляется.  Например, если будет указано 0x11110001, оно округляется до 0x11110000.  
  
 Для подписывания библиотеки DLL используйте опцию `–R` инструмента строгого именования \(Sn.exe\).  
  
 Этот параметр пропускается, если конечный файл не является DLL.  
  
||  
|-|  
|Чтобы установить параметр \/baseaddress в Visual Studio IDE|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в поле **Базовый адрес DLL** . **Note:**      **Базовый адрес DLL:** поле доступно только для чтения, если целевым является не DLL\-файл.|  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)