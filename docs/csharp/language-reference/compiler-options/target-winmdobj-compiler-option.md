---
title: "/target:winmdobj (параметры компилятора C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /target:winmdobj (параметры компилятора C#)
Если используется параметр компилятора **\/target:winmdobj**, компилятор создает промежуточный WINMDOBJ\-файл, который можно преобразовать в бинарный WINMD\-файл среды выполнения Windows.  Затем WINMD\-файл можно использовать в программах на языках JavaScript и C\+\+ в дополнение к программам, использующим управляемые языки.  
  
## Синтаксис  
  
```  
/target:winmdobj  
```  
  
## Заметки  
 Параметр **winmdobj** сигнализирует компилятору, что необходим промежуточный модуль.  В результате Visual Studio компилирует библиотеку классов C\# в виде WINMDOBJ\-файла.  Затем WINMDOBJ\-файл можно обработать с помощью инструмента экспорта <xref:Microsoft.Build.Tasks.WinMDExp> для создания файла метаданных Windows \(WINCMD\-файл\).  WINMD\-файл содержит код из исходной библиотеки и метаданные WinMD, используемые JavaScript, C\+\+ и средой выполнения Windows.  
  
 Выходные данные файла, скомпилированного с помощью параметра **\/target:winmdobj**, предназначены только для использования в качестве входных данных инструментом экспорта WimMDExp \(на WINMDOBJ\-файл нет прямой ссылки\).  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  Метод [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) не требуется.  
  
 Если параметр \/target:winmdobj указан в командной строке, все файлы до следующего параметра **\/out** или [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) будут использоваться для создания программы Windows.  
  
### Установка данного параметра компилятора в интегрированной среде разработки Visual Studio для приложения для Магазина Windows  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите **Свойства**.  
  
2.  Перейдите на вкладку **Приложение**.  
  
3.  В списке **Тип выходных данных** выберите **Файл WinMD**.  
  
     Параметр **Файл WinMD** доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)].  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 Следующая команда компилирует `filename.cs` в промежуточный WINMDOBJ\-файл.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)