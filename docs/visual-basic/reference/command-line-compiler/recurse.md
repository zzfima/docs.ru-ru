---
title: "/recurse | Microsoft Docs"
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
  - "/recurse - параметр компилятора [Visual Basic]"
  - "recurse - параметр компилятора [Visual Basic]"
  - "-recurse - параметр компилятора [Visual Basic]"
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# /recurse
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Компилирует файлы исходного кода, содержащиеся во всех дочерних папках, либо в указанной папке, либо в папке проекта.  
  
## Синтаксис  
  
```  
/recurse:[dir\]file  
```  
  
## Аргументы  
 `dir`  
 Необязательный.  Папка, в которой следует начать поиск.  Если не указана, поиск начинается в папке проекта.  
  
 `file`  
 Обязательный.  Файлы, которые нужно найти.  Допускается использование специальных знаков.  
  
## Заметки  
 Для компиляции всех файлов из папки проекта без использования параметра `/recurse` в имени файла можно использовать специальные знаки.  Если имя выходного файла не задано, компилятор использует имя первого обработанного файла с входными данными.  Как правило, это первый файл из списка скомпилированных файлов, расположенных в алфавитном порядке.  По этой причине лучше всего задать выходной файл с помощью параметра `/out`.  
  
> [!NOTE]
>  Параметр `/recurse` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 В следующем примере кода выполняется компиляция всех файлов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в текущей папке.  
  
```  
vbc *.vb  
```  
  
 Следующий код компилирует все файлы [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в каталоге `Test\ABC` и во всех вложенных каталогах и создает `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)