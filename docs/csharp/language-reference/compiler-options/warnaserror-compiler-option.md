---
title: "/warnaserror (C# Compiler Options) | Microsoft Docs"
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
  - "/warnaserror"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/warnaserror compiler option [C#]"
  - "-warnaserror compiler option [C#]"
  - "warnaserror compiler option [C#]"
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /warnaserror (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/warnaserror\+** обрабатывает все предупреждения как ошибки  
  
## Синтаксис  
  
```  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## Заметки  
 Все сообщения, которые обычно рассматриваются как предупреждения, выводятся как ошибки и процесс построения останавливается \(выходные файлы не создаются\).  
  
 По умолчанию действует параметр **\/warnaserror\-**, в результате чего предупреждения не мешают генерированию выходного файла.  Параметр **\/warnaserror** равнозначный параметру **\/warnaserror\+**, приводит к тому, что предупреждения обрабатываются как ошибки.  
  
 В качестве варианта, если требуется обрабатывать как ошибки только несколько определенных предупреждений, то можно задать разделенный запятыми список номеров предупреждений, которые следует обрабатывать как ошибки.  
  
 Для определения уровня предупреждений, которые компилятор должен выводить на экран, используется параметр [\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md).  Для отключения определенных предупреждений используется параметр [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Измените значение свойства **Обрабатывать предупреждения как ошибки**.  
  
     Сведения об установке этого параметра компилятора программным способом см. в описании свойства <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.  
  
## Пример  
 Скомпилируйте файл `in.cs` без отображения компилятором предупреждений:  
  
```  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)