---
title: "How to: Set Environment Variables for the Visual Studio Command Line | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.build.commandline"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "csc.exe, command-line builds"
  - "Visual C#, command-line builds"
  - "command-line compilers, Visual C#"
  - "Vsvars32.bat"
  - "builds [C#], command-line"
  - "compilers, invoking from command line"
  - "Vcvars32.bat file"
  - "command line [C#], building from"
  - "Visual C# compiler, enabling"
  - "compiling source code, from command line"
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# How to: Set Environment Variables for the Visual Studio Command Line
Файл vsvars32.bat задает переменные среды для поддержки построения из командной строки.  Дополнительные сведения о vsvars32.bat см. в [статье базы знаний Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  
  
 Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл vsvars32.bat или vcvars32.bat из других версий в том же окне командной строки.  
  
### Запуск VSVARS32.BAT  
  
1.  В меню **Пуск** выберите пункт **Командная строка разработчика для VS2012**.  
  
2.  Перейдите в подкаталог Program Files\\Microsoft Visual Studio *версия*\\Common7\\Tools или Program Files \(x86\)\\Microsoft Visual Studio *версия*\\Common7\\Tools установочного каталога.  
  
3.  Введите VSVARS32, чтобы запустить файл VSVARS32.bat.  
  
    > [!CAUTION]
    >  Файл VSVARS32.bat может иметь отличия на разных компьютерах.  Не заменяйте отсутствующий или поврежденный файл VSVARS32.bat файлом VSVARS32.bat с другого компьютера.  Вместо этого повторите установку, чтобы заменить отсутствующий файл.  
  
## См. также  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)