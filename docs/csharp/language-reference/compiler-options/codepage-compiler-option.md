---
title: "/codepage (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/codepage"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/codepage compiler option [C#]"
  - "codepage compiler option [C#]"
  - "-codepage compiler option [C#]"
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /codepage (C# Compiler Options)
Этот параметр определяет, какая кодовая страница должна использоваться при компиляции, если требуемая страница не является системной кодовой страницей.  
  
## Синтаксис  
  
```  
/codepage:id  
```  
  
## Аргументы  
 `id`  
 Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.  
  
## Заметки  
 При компиляции одного или нескольких файлов исходного кода, которые не предназначены для использования системной кодовой страницы компьютера, можно воспользоваться параметром **\/codepage**, чтобы указать необходимую кодовую страницу.  Параметр **\/codepage** применяется ко всем файлам при компиляции исходного кода.  
  
 Если файлы исходного кода были созданы с помощью одной кодовой страницы, которая установлена на компьютере, или файлы исходного кода были созданы с помощью кодовых страниц ЮНИКОД или UTF\-8, использовать параметр **\/codepage** не требуется.  
  
 См. в разделе [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) сведения о том, как найти кодовые страницы, которые поддерживаются в системе.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)