---
title: "/moduleassemblyname | Microsoft Docs"
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
  - "/moduleassemblyname - параметр компилятора [Visual Basic]"
  - "moduleassemblyname - параметр компилятора [Visual Basic]"
  - "-moduleassemblyname - параметр компилятора [Visual Basic]"
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /moduleassemblyname
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задается имя сборки, частью которой будет данный модуль.  
  
## Синтаксис  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`assembly_name`|Имя сборки, частью которой будет данный модуль.|  
  
## Заметки  
 Компилятор обрабатывает параметр `/moduleassemblyname` только в том случае, если был задан параметр `/target:module`.  Он указывает компилятору, что нужно создать модуль.  Модуль, созданный компилятором, является допустимым только для сборки, указанной в параметре `/moduleassemblyname`.  Если поместить модуль в другую сборку, это приведет к появлению ошибок во время выполнения.  
  
 Параметр `/moduleassemblyname` необходим только при наличии следующих условий:  
  
-   Для типа данных в модуле необходим доступ к типу `Friend` в указанной сборке.  
  
-   Указанной сборкой предоставлен дружественной сборке доступ к сборке, в которую будет встроен модуль.  
  
 Дополнительные сведения о создании модуля см. в разделе [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  Дополнительные сведения о дружественных сборках см. в разделе [Дружественные сборки](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
> [!NOTE]
>  Параметр `/moduleassemblyname` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## См. также  
 [Практическое руководство. Создание многофайловой сборки](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Дружественные сборки](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)