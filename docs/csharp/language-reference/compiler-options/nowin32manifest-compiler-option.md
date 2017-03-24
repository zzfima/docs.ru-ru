---
title: "/nowin32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/nowin32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowin32manifest compiler option [C#]"
  - "-nowin32manifest compiler option [C#]"
  - "/nowin32manifest compiler option [C#]"
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /nowin32manifest (C# Compiler Options)
При помощи параметра **\/nowin32manifest** можно указать компилятору не встраивать какой\-либо манифест приложения в исполняемый файл.  
  
## Синтаксис  
  
```  
/nowin32manifest  
```  
  
## Заметки  
 Если эта опция используется, приложение будет предметом для виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах построения.  Дополнительные сведения о виртуализации см. в разделе [New UAC Technologies for Windows Vista](http://msdn.microsoft.com/ru-ru/80efa4c7-3904-45c5-82e8-2d558fe67db9).  
  
 В Visual Studio этот параметр можно задать на странице **Свойств компилятора**, выбрав пункт **Создать приложение без манифеста** из раскрывающегося списка **Манифест**.  Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Дополнительные сведения о создании манифестов см. в разделе [\/win32manifest \(Import a Custom Win32 Manifest File\)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)