---
title: "/reference (Visual Basic) | Microsoft Docs"
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
  - "/r - параметр компилятора [Visual Basic]"
  - "/reference - параметр компилятора [Visual Basic]"
  - "r - параметр компилятора [Visual Basic]"
  - "-r - параметр компилятора [Visual Basic]"
  - "reference - параметр компилятора [Visual Basic]"
  - "-reference - параметр компилятора [Visual Basic]"
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает компилятору сделать доступными для текущего компилируемого проекта сведения о типе, находящиеся в указанных сборках.  
  
## Синтаксис  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`fileList`|Обязательный.  Список имен файлов сборки с элементами отделенными между собой запятыми.  Заключите имя файла в кавычки \(""\), если оно содержит пробел.|  
  
## Заметки  
 Импортируемые файлы должны содержать метаданные сборки.  Вне сборки видны только открытые типы.  Параметр [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) импортирует метаданные из модуля.  
  
 При ссылке на сборку А, которая, в свою очередь, ссылается на сборку Б, необходимо ссылаться на сборку Б в следующих случаях:  
  
-   Используемый из сборки A тип наследуется от типа или реализует интерфейс из сборки Б.  
  
-   Вызывается поле, свойство, событие или метод, который возвращает из сборки Б тип или параметр типа.  
  
 Для указания каталога, в котором находятся сборки, на которые производятся ссылки, служит параметр [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md).  
  
 Для распознавания компилятором типа в сборке \(не в модуле\), он должен иметь возможность для уточнения типа.  Одним из примеров того, как это можно сделать является определение экземпляра типа.  Для уточнения имен типов в сборке существуют также другие способы.  Например, если имя типа наследуется из типа сборки, то оно становится известно компилятору.  
  
 Файл ответов Vbc.rsp, который содержит ссылки на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], используется по умолчанию.  Если не требуется, чтобы компилятор использовал файл Vbc.rsp, применяйте `/noconfig`.  
  
 `/r` является короткой формой `/reference` .  
  
## Пример  
 Следующий код компилирует исходный файл I`nput.vb` и ссылается на сборки из M`etad1.dll` и M`etad2.dll` для получения O`ut.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)