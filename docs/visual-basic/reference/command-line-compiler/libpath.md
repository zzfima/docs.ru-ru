---
title: "/libpath | Microsoft Docs"
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
  - "/libpath - параметр компилятора [Visual Basic]"
  - "libpath - параметр компилятора [Visual Basic]"
  - "-libpath - параметр компилятора [Visual Basic]"
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /libpath
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает расположение сборок, на которые указывают ссылки.  
  
## Синтаксис  
  
```  
/libpath:dirList  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`dirList`|Обязательный.  Список каталогов, разделенный точкой с запятой, указывающий где компилятор должен искать сборку, если она отсутствует в текущей рабочей папке \(папке, из которой был вызван компилятор\) или системной папке общей среды выполнения.  Если имя каталога содержит пробел, заключите имя в кавычки \(" "\).|  
  
## Заметки  
 Параметр `/libpath` указывает расположение сборок, на которые ссылается параметр [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md).  
  
 Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке.  
  
1.  Текущая рабочая папка.  Это папка, из которой был вызван компилятор.  
  
2.  Системный каталог среды CLR.  
  
3.  Каталоги, заданные по `/libpath`.  
  
4.  Каталоги, указанные переменной среды LIB.  
  
 Параметр `/libpath` является аддитивным; при его многократном указании он добавляется к предыдущим значениям.  
  
 Используйте `/reference` для указания ссылки на сборку.  
  
||  
|-|  
|Установка \/libpath в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Нажмите кнопку **Пути для ссылок**.<br />4.  В диалоговом окне **Пути для ссылок** введите имя каталога в поле **Папка:**.<br />5.  Нажмите кнопку **Добавить папку**.|  
  
## Пример  
 В следующем примере кода производится компиляция `T2.vb` для создания файла .exe.  Компилятор выполняет поиск ссылок на сборку в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске C:.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## См. также  
 [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)