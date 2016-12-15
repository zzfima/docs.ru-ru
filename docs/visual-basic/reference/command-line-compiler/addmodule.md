---
title: "/addmodule | Microsoft Docs"
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
  - "/addmodule - параметр компилятора [Visual Basic]"
  - "addmodule - параметр компилятора [Visual Basic]"
  - "-addmodule - параметр компилятора [Visual Basic]"
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /addmodule
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Делает доступными все сведения из указанных файлов для компилируемого проекта.  
  
## Синтаксис  
  
```  
/addmodule:fileList  
```  
  
## Аргументы  
 `fileList`  
 Обязательный.  Список файлов, разделяемых запятыми, которые содержат метаданные, но не содержат манифестов сборки.   Имена файлов, содержащие пробелы, должны быть заключены в кавычки \(" "\).  
  
## Заметки  
 Перечисленные файлы с помощью параметра `fileList` должны создаваться с параметром `/target:module` или другим эквивалентом компилятора `/target:module`.  
  
 Все модули, добавленные при помощи `/addmodule`, во время выполнения должны находиться в той же папке, что и выходной файл.  Таким образом, во время компиляции можно указать модуль в любой папке, но во время выполнения он должен находиться в папке приложения.  Если это не так, появится сообщение об ошибке <xref:System.TypeLoadException>.  
  
 Если явно или неявно указан какой\-либо параметр [\/target](../../../visual-basic/reference/command-line-compiler/target.md), отличный от `/target:module` с `/addmodule`, то файлы, передаваемые в `/addmodule`, становятся частью сборки проекта.  Сборка требуется для выполнения выходного файла, к которому были добавлены файлы при помощи параметра `/addmodule`.  
  
 Используйте [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
>  Параметр `/addmodule` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 В следующем коде создается модуль.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 При выполнении `t1` выводится `802`.  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)