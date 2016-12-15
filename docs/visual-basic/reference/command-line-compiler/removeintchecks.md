---
title: "/removeintchecks | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "removeintchecks"
  - "/removeintchecks"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/removeintchecks - параметр компилятора [Visual Basic]"
  - "removeintchecks - параметр компилятора [Visual Basic]"
  - "-removeintchecks - параметр компилятора [Visual Basic]"
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /removeintchecks
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Включает или отключает проверку ошибок на переполнение для целочисленных операций.  
  
## Синтаксис  
  
```  
/removeintchecks[+ | -]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`+`  &#124; `-`|Необязательный.  `/removeintchecks-` параметр указывает компилятору проверить все вычисления целого числа для ошибок переполнения.  Значение по умолчанию: `/removeintchecks-`.<br /><br /> Задание `/removeintchecks` или `/removeintchecks+` предотвращает проверку ошибок и увеличивает скорость целочисленных вычислений.  Однако, если проверка ошибок не производится и возникает переполнение диапазона типа данных, будут сохранены неверные результаты и не будет выдано сообщение об ошибке.|  
  
||  
|-|  
|Чтобы установить параметр \/removeintchecks в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение **Удалить проверку переполнения целых чисел**.|  
  
## Пример  
 Следующий код компилирует `Test.vb` и отключает проверку переполнения целых чисел.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)