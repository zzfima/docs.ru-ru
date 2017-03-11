---
title: "/nowarn (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/nowarn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowarn compiler option [C#]"
  - "/nowarn compiler option [C#]"
  - "-nowarn compiler option [C#]"
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# /nowarn (C# Compiler Options)
Параметры **\/nowarn** позволяет предотвратить отображение одного или нескольких предупреждений компилятором.  Отделите предупреждения друг от друга запятыми.  
  
## Синтаксис  
  
```  
/nowarn:number1[,number2,...]  
```  
  
## Аргументы  
 `number1`, `number2`  
 Номер \(номера\) предупреждений, которые требуется отключить в компиляторе.  
  
## Заметки  
 Необходимо указать только числовую часть идентификатора предупреждения.  Например если требуется отключить CS0028, можно указать `/nowarn:28`.  
  
 Компилятор просто пропустит номера предупреждений, переданные `/nowarn`, которые использовались в предыдущих версиях, но были удалены из компилятора.  Например, CS0679 использовался компилятором в Visual Studio .NET 2002, но в последующих версиях был исключен.  
  
 Параметр `/nowarn` позволяет отключить следующие предупреждения:  
  
-   Предупреждение компилятора \(уровень 1\) CS2002  
  
-   Предупреждение компилятора \(уровень 1\) CS2023  
  
-   Предупреждение компилятора \(уровень 1\) CS2029  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  Дополнительные сведения см. в разделе [Страница "Построение" в конструкторе проектов \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Измените свойство **Отключить предупреждения**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)