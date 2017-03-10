---
title: "/langversion (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/langversion"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/langversion compiler option [C#]"
  - "-langversion compiler option [C#]"
  - "langversion compiler option [C#]"
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# /langversion (C# Compiler Options)
Принуждает компилятор принимать только синтаксис, включенный в выбранную спецификацию языка C\#.  
  
## Синтаксис  
  
```  
/langversion:option  
```  
  
## Аргументы  
 `option`  
 Допустимы следующие значения.  
  
|Команда|Значение|  
|-------------|--------------|  
|default|Компилятор допускает использование любого допустимого синтаксиса языка.|  
|ISO\-1|Компилятор принимает только синтаксис, включенный в спецификацию языка C\# ISO\/IEC 23270:2003.|  
|ISO\-2|Компилятор принимает только синтаксис, включенный в спецификацию языка C\# ISO\/IEC 23270:2006.  Эта спецификация доступна на веб\-сайте [ISO](http://go.microsoft.com/fwlink/?LinkId=144406).|  
|3|Компилятор принимает только синтаксис, включенный в версию 3.0 [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md).|  
  
## Заметки  
 Метаданные, на которые ссылается приложение C\#, не регулируются параметром компилятора **\/langversion**.  
  
 Поскольку каждая версия компилятора C\# включает расширения спецификации языка, **\/langversion** не обеспечивает набор возможностей, эквивалентный набору более ранней версии.  
  
 Независимо от того, какой параметр **\/langversion** вы используете, для создания файлов .exe или .dll будет использоваться текущая версия среды выполнения.  Единственным исключением являются дружественные построения и [\/moduleassemblyname \(Specify Friend Assembly for Module\)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), работающие в соответствии с **\/langversion:ISO\-1**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Версия языка**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md)