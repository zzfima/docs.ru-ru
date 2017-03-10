---
title: "/win32res (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32res"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32res compiler option"
  - "/win32res compiler option [C#]"
  - "-win32res compiler option [C#]"
  - "win32res compiler option [C#]"
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /win32res (C# Compiler Options)
Параметр **\/win32res** вставляет ресурс Win32 в выходной файл.  
  
## Синтаксис  
  
```  
/win32res:filename  
```  
  
## Аргументы  
 `filename`  
 Файл ресурсов, который следует добавить в выходной файл.  
  
## Заметки  
 Файл ресурсов Win32 может быть создан [Компилятором ресурсов](http://go.microsoft.com/fwlink/?LinkId=148370).  Компилятор ресурсов вызывается при компиляции программы Visual C\+\+; RES\-файл создается из RC\-файла.  
  
 Ресурс Win32 может содержать версию или графическое изображение \(значок\) для упрощения идентификации приложения в проводнике.  Если параметр **\/win32res** не указан, компилятор формирует сведения о версии на основе версии сборки.  
  
 Сведения о файлах ресурсов .NET Framework см. в разделе [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) \(о создании ссылки\) или [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) \(о присоединении\).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Приложение**.  
  
3.  Нажмите кнопку **Файл ресурсов** и выберите файл с помощью поля со списком.  
  
## Пример  
 Компиляция файла `in.cs` и присоединение файла ресурсов Win32 `rf.res` для создания файла `in.exe`.  
  
```  
csc /win32res:rf.res in.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)