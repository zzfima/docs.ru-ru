---
title: "/target:appcontainerexe (параметры компилятора C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /target:appcontainerexe (параметры компилятора C#)
Если используется параметр компилятора **\/target:appcontainerexe**, компилятор создает исполняемый файл Windows \(EXE\-файл\), который должен запускаться в контейнере приложения.  Этот параметр аналогичен [\/target: winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), но предназначен для приложений под [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)].  
  
## Синтаксис  
  
```  
/target:appcontainerexe  
```  
  
## Заметки  
 Этот параметр \(бит\) задает соответствующее значение в [переносимом исполняемом файле](http://go.microsoft.com/fwlink/p/?LinkId=236960) \(PE\), чтобы обеспечить запуск приложения в контейнере.  Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.  
  
 Выходной файл получает имя входного файла, содержащего метод [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md), если только с помощью параметра [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Если этот параметр указан в командной строке, все файлы до следующего параметра **\/out** или **\/target** будут использоваться для создания исполняемого файла.  
  
### Установка данного параметра компилятора в интегрированной среде разработки  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите **Свойства**.  
  
2.  На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.  
  
     Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)].  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Пример  
 Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## См. также  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [\/target:winexe \(Create a Windows Program\)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)