---
title: "/win32icon | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "/win32icon - параметр компилятора [Visual Basic]"
  - "win32icon - параметр компилятора [Visual Basic]"
  - "-win32icon - параметр компилятора [Visual Basic]"
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32icon
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Добавляет файл ICO к выходному файлу.  Этот файл ico представляет выходной файл, в **\*\*\* В обозревателе файла \*\*\***.  
  
## Синтаксис  
  
```  
/win32icon:filename  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`filename`|Имя файла ICO, который добавляется к выходному файлу.  Если имя файла содержит пробел, следует заключить его в кавычки \(" "\).|  
  
## Заметки  
 Файл ICO можно создать с помощью компилятора ресурсов Microsoft Windows.  Компилятор ресурсов вызывается при компиляции программы, написанной с помощью Visual C\+\+; файл ICO создается из файла с расширением RC.  Параметры `/win32icon` и `/win32resource` являются взаимоисключающими.  
  
 Сведения о создании ссылки на файл ресурсов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] см. в разделе [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md), а сведения о присоединении файла ресурсов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] — в разделе [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md).  Сведения об импорте файла RES см. в разделе [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md).  
  
||  
|-|  
|Чтобы установить параметр \/ win32icon в интегрированной среде разработки Visual Studio|  
|1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение**.<br />3.  Измените значение в поле **Значок**.|  
  
## Пример  
 В следующем коде выполняется компиляция `In.vb` и присоединяется файл ICO \(`Rf.ico`\).  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)