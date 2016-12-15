---
title: "/nowarn | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/nowarn - параметр компилятора [Visual Basic]"
  - "nowarn - параметр компилятора [Visual Basic]"
  - "-nowarn - параметр компилятора [Visual Basic]"
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /nowarn
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Отключает предупреждения компилятора.  
  
## Синтаксис  
  
```  
/nowarn[:numberList]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`numberList`|Необязательный.  Список отделенных друг от друга запятыми идентификационных номеров предупреждений, которые компилятор не должен отображать.  Если идентификаторы предупреждений не указаны, то подавляются все предупреждения.|  
  
## Заметки  
 Параметр `/nowarn` указывает компилятору не генерировать предупреждения.  Для подавления отдельных предупреждений, укажите идентификатор предупреждения для параметра `/nowarn` после двоеточия.  Отделите предупреждения друг от друга запятыми.  
  
 Необходимо указать только числовую часть идентификатора предупреждения.  Например, если требуется подавить BC42024, предупреждение для неиспользуемых локальных переменных, укажите `/nowarn:42024`.  
  
 Дополнительные сведения об идентификаторах предупреждений содержатся в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
||  
|-|  
|Чтобы установить параметр \/nowarn в среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Выберите флажок **Отключить все предупреждения**, чтобы отключить все предупреждения.<br />     \- или \-<br />     Чтобы отключить определенное предупреждение, установите переключатель в положение **Нет** в раскрывающемся списке рядом с предупреждением.|  
  
## Пример  
 Следующий код компилирует `T2.vb`, не отображая предупреждений.  
  
```  
vbc /nowarn t2.vb  
```  
  
## Пример  
 Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных \(42024\).  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic)