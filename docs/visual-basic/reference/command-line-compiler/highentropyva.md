---
title: "/highentropyva (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/highentropyva - параметр компилятора (Visual Basic)"
  - "highentropyva - параметр компилятора (Visual Basic)"
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /highentropyva (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Показывает, поддерживает ли 64 исполняемый файл или исполняемого файла, отмечается параметром компилятора [\/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) высокий Randomization структуры адресного пространства \(ASLR энтропии\).  
  
## Синтаксис  
  
```  
/highentropyva[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Параметр со значением по умолчанию или при указании `/highentropyva-`.  Параметр on при указании `/highentropyva` или `/highentropyva+`.  
  
## Заметки  
 Если указан этот параметр, то совместимые версии ядра windows, могут использовать более высокие degrees энтропии, когда компонент database хаотизирует структуру адресного пространства процесса как часть ASLR.  Если компонент database используется более высокие degrees энтропии, большее количество адресов можно выбрать к областям памяти как стеки и кучи.  В результате сложнее угадать расположение указанной области памяти.  
  
 Если параметр on, целевой объект и исполняемый все модули, на котором он зависит, должны иметь возможность обрабатывать значения указателя, превышающие 4 гигабайт \(ГБ\), если эти модули запускаются как 64 процессов.  
  
 Дополнительные сведения о ASLR см. в разделе [Сдерживание уязвимости программного обеспечения](http://go.microsoft.com/fwlink/?LinkId=226234).  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)