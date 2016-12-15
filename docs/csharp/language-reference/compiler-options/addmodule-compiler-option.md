---
title: "/addmodule (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/addmodule"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/addmodule compiler option [C#]"
  - "-addmodule compiler option [C#]"
  - "addmodule compiler option [C#]"
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /addmodule (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Установка этого параметра приводит к добавлению модуля, созданного с помощью параметра target:module для текущей компиляции.  
  
## Синтаксис  
  
```  
/addmodule:file[;file2]  
```  
  
## Аргументы  
 `file`, `file2`  
 Выходной файл, содержащий метаданные.  В данный файл не может входить манифест сборки.  Чтобы импортировать несколько файлов, разделите их имена запятыми или точками с запятой.  
  
## Заметки  
 Все модули, добавленные при помощи **\/addmodule**, во время выполнения должны находиться в той же папке, что и выходной файл.  То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения.  Если во время выполнения модуль отсутствует в каталоге приложения, возникнет <xref:System.TypeLoadException>.  
  
 `file` не может содержать сборку.  Например, если выходной файл был создан с помощью [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), для импорта его метаданных можно использовать **\/addmodule**.  
  
 Если выходной файл был создан с помощью параметра **\/target**, отличного от **\/target:module**, для импорта его метаданных нельзя использовать **\/addmodule**, но можно [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Этот параметр компилятора недоступен в Visual Studio; проект не может ссылаться на модуль.  Кроме того, этот параметр компилятора нельзя изменить программным способом.  
  
## Пример  
 Скомпилируйте исходный файл `input.cs` и добавьте метаданные из `metad1.netmodule` и `metad2.netmodule`, чтобы создать `out.exe`.  
  
```  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Многофайловые сборки](../Topic/Multifile%20Assemblies.md)   
 [Практическое руководство. Создание многофайловой сборки](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)