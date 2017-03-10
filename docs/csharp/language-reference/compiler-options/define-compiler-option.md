---
title: "/define (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-define compiler option [C#]"
  - "/define compiler option [C#]"
  - "-d compiler option [C#]"
  - "define compiler option [C#]"
  - "/d compiler option [C#]"
  - "d compiler option [C#]"
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# /define (C# Compiler Options)
Параметр **\/define** определяет `name` как символ во всех файлах исходного кода программы.  
  
## Синтаксис  
  
```  
/define:name[;name2]  
```  
  
## Аргументы  
 `name`, `name2`  
 Имя из одного или нескольких символов, которые требуется определить.  
  
## Заметки  
 Параметр **\/define** оказывает такое же влияние, что и использование директивы препроцессора [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), за исключением того, что параметр компилятора влияет на все файлы проекта.  Этот символ остается определенным в исходном файле до тех пор, пока директива [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) в исходном файле не удалит определение.  При использовании параметра \/define директива `#undef` в одном файле не влияет на другие файлы исходного кода в проекте.  
  
 Созданные с помощью этого параметра символы можно использовать с директивами [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) и [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) для условной компиляции исходного кода.  
  
 **\/d** является короткой формой **\/define**.  
  
 Можно определить несколько символов при помощи параметра **\/define**, отделяя имена символов точкой с запятой или запятой.  Примеры.  
  
```  
/define:DEBUG;TUESDAY  
```  
  
 Сам компилятор C\# не определяет символы или макросы, используемые в исходном коде; все определения символов должны быть заданы пользователем.  
  
> [!NOTE]
>  В C\# директива `#define` не позволяет присвоить символу значение, в отличие от других языков, таких как C\+\+.  Например, `#define` не может использоваться для создания макроса или определения константы.  Для определения константы необходимо использовать переменную `enum`.  Для создания макросов в стиле C\+\+ можно использовать альтернативные варианты, такие как универсальные шаблоны.  Поскольку макросы заведомо являются источниками ошибок, в C \# запрещено их использование, но предоставлены более безопасные альтернативы.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  На вкладке **Построение** введите символ, который должен быть определен в поле **Символы условной компиляции**.  Например, при использовании показанного далее примера кода просто введите в текстовое поле `xx`.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## Пример  
  
```  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)