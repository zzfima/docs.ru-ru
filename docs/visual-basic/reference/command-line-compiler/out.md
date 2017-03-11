---
title: "/out (Visual Basic) | Microsoft Docs"
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
  - "/out - параметр компилятора [Visual Basic]"
  - "out - параметр компилятора [Visual Basic]"
  - "-out - параметр компилятора [Visual Basic]"
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /out (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает имя выходного файла.  
  
## Синтаксис  
  
```  
/out:filename  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`filename`|Обязательный.  Имя выходного файла, создаваемого компилятором.  Заключите имя файла в кавычки \(" "\), если оно содержит пробел.|  
  
## Заметки  
 Необходимо задать полное имя и расширение создаваемого файла.  Если этого не сделать, для имени ЕХЕ\-файла будет использовано имя файла исходного кода, который содержит процедуру `Sub Main`, а для имени DLL\-файла — имя первого файла исходного кода.  
  
 Если задать имя файла без расширения EXE или DLL, компилятор автоматически добавит расширение в зависимости от значения, заданного для параметра компилятора `/target`.  
  
||  
|-|  
|Установить\/исключить параметр в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение**.<br />3.  Измените значение в поле **Имя сборки**.|  
  
## Пример  
 Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)