---
title: "/rootnamespace | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rootnamespace"
  - "rootnamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/rootnamespace - параметр компилятора [Visual Basic]"
  - "rootnamespace - параметр компилятора [Visual Basic]"
  - "-rootnamespace - параметр компилятора [Visual Basic]"
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /rootnamespace
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает пространство имен для всех объявлений типов.  
  
## Синтаксис  
  
```  
/rootnamespace:namespace  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`namespace`|Имя пространства имен, в котором должны находиться все объявления типов текущего проекта.|  
  
## Заметки  
 Если для компиляции проекта, созданного в среде разработки Visual Studio, используется исполняемый файл Visual Studio \(Devenv.exe\), то для задания значения свойства <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> следует использовать параметр `/rootnamespace`.  Дополнительные сведения см. в разделе [Параметры командной строки для команды Devenv](/visual-studio/ide/reference/devenv-command-line-switches).  
  
 Для просмотра имен пространств имен в выходном файле служит программа дизассемблера MSIL \(`ldasm.exe`\) среды CLR.  
  
||  
|-|  
|Использование параметра \/rootnamespace в среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение**.<br />3.  Измените значение в поле **Корневое пространство имен**.|  
  
## Пример  
 Следующий код компилирует `In.vb` и помещает все объявления типов в пространство имен `mynamespace`.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe \(IL Disassembler\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)