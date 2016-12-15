---
title: "/win32icon (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/win32icon"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32icon compiler option [C#]"
  - "/win32icon compiler option [C#]"
  - "-win32icon compiler option [C#]"
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32icon (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/win32icon** вставляет в выходной ICO\-файл, который придает выходному файлу требуемый вид в проводнике.  
  
## Синтаксис  
  
```  
/win32icon:filename  
```  
  
## Аргументы  
 `filename`  
 ICO\-файл, который следует добавить в выходной файл.  
  
## Заметки  
 Ico\-файл можно создать с помощью [Компилятора ресурсов](http://go.microsoft.com/fwlink/?LinkId=148370).  Компилятор ресурсов вызывается при компиляции программы, написанной на языке Visual C\+\+; ICO\-файл создается из RC\-файла.  
  
 Сведения о файлах ресурсов .NET Framework см. в разделе [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) \(о создании ссылки\) или [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) \(о присоединении\).  Сведения об импорте RES\-файла см. в разделе [\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Измените значение свойства **Значок приложения**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## Пример  
 Компиляция файла `in.cs` и присоединение ICO\-файла `rf.ico`, чтобы получить файл `in.exe`:  
  
```  
csc /win32icon:rf.ico in.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)