---
title: "/define (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/d - параметр компилятора [Visual Basic]"
  - "/define - параметр компилятора [Visual Basic]"
  - "d - параметр компилятора [Visual Basic]"
  - "-d - параметр компилятора [Visual Basic]"
  - "define параметр компилятора [Visual Basic]"
  - "-define параметр компилятора [Visual Basic]"
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /define (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает константы условной компиляции.  
  
## Синтаксис  
  
```  
/define:["]symbol[=value][,symbol[=value]]["] ' -or- /d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`symbol`|Обязательный.  Определяемый символ.|  
|`value`|Необязательно.  Значение, которому назначается `symbol`.  Если `value` является строкой, его необходимо заключить в последовательности из обратной косой черты и кавычки \(\\"\), а не просто в кавычки.  Если значение не задано, считается, что используется значение True.|  
  
## Заметки  
 Влияние параметра `/define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `/define` константы являются общими и применяются ко всем файлам в проекте.  
  
 Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.  
  
 `/d` является краткой формой `/define`.  
  
 Вы можете определить несколько символов с помощью `/define`, разделяя их определения запятой.  
  
||  
|-|  
|Задание параметра \/define в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **Обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Для получения дополнительной информации см. [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в поле **Настраиваемые константы**.|  
  
## Пример  
 В следующем примере кода определяются и используются две константы условной компиляции.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Директива \#Const](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)