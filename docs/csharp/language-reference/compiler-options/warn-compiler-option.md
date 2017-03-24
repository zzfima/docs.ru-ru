---
title: "/warn (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "warning level [C#]"
  - "/w compiler option [C#]"
  - "-w compiler option [C#]"
  - "-warn compiler option [C#]"
  - "/warn compiler option [C#]"
  - "w compiler option [C#]"
  - "warn compiler option [C#]"
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /warn (C# Compiler Options)
Параметр **\/warn** задает уровень предупреждений, которые должны отображаться компилятором.  
  
## Синтаксис  
  
```  
/warn:option  
```  
  
## Аргументы  
 `option`  
 Уровень предупреждений, отображаемых при компиляции: чем меньше число, тем выше уровень серьезности предупреждения.  Допустимые значения: от 0 до 4.  
  
|Уровень предупреждений|Значение|  
|----------------------------|--------------|  
|0|Отключает вывод всех предупреждающих сообщений.|  
|1|Выводит важные предупреждающие сообщения.|  
|2|Выводит предупреждения уровня 1 и различные менее серьезные предупреждения, например предупреждения о скрытии элементов класса.|  
|3|Выводит предупреждения уровня 2 и различные менее серьезные предупреждения, например предупреждения о выражениях, всегда имеющих значение `true` или `false`.|  
|4 \(значение по умолчанию\)|Выводит все предупреждения уровня 3 и информационные предупреждения.|  
  
## Заметки  
 Для получения информации об ошибке или предупреждении найдите код ошибки в указателе справки.  Дополнительные способы получения сведения об ошибках и предупреждениях см. в разделе [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).  
  
 Используйте [\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md), чтобы обрабатывать все предупреждения как ошибки.  Для отключения определенных предупреждений используется параметр [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md).  
  
 **\/w** является короткой формой **\/warn**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Измените свойство **Порог предупреждений**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## Пример  
 Компиляция файла `in.cs` с отображением только предупреждений уровня 1:  
  
```  
csc /warn:1 in.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)