---
title: "/optimize | Microsoft Docs"
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
  - "/optimize - параметр компилятора [Visual Basic]"
  - "оптимизация, включение"
  - "optimize - параметр компилятора [Visual Basic]"
  - "-optimize - параметр компилятора [Visual Basic]"
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optimize
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Включает или отключает оптимизацию компилятора.  
  
## Синтаксис  
  
```  
/optimize[ + | - ]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`+`  &#124; `-`|Необязательный.  Параметр `/optimize-` отключает оптимизацию компилятора.  Параметр `/optimize+` включает оптимизацию.  По умолчанию оптимизация отключена.|  
  
## Заметки  
 Оптимизация кода делает код более быстрым, коротким и более эффективным.  Однако из\-за изменения порядка строк кода при его оптимизации `/optimize+` может осложнить процесс отладки.  
  
 Все модули, созданные для сборки с помощью `/target:module`, должны использовать те же параметры `/optimize`, что и сборка.  Дополнительные сведения см. в разделе [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Пользователь может объединить параметры `/optimize` и `/debug`.  
  
||  
|-|  
|Чтобы установить \/optimize в среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.<br />     Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Compile**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените флажок **Включить оптимизацию**.|  
  
## Пример  
 Следующий код компилирует `T2.vb` и включает оптимизацию.  
  
```  
vbc t2.vb /optimize  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)