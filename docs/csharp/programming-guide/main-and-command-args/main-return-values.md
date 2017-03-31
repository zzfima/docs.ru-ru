---
title: "Значения, возвращаемые методом Main() (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 846c52b7d5429a23f354dd6a732ddb62563a55bf
ms.lasthandoff: 03/13/2017

---
# <a name="main-return-values-c-programming-guide"></a>Значения, возвращаемые методом Main() (Руководство по программированию на C#)
Метод `Main` может возвращать значение `void`:  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 Он также может возвращать значение типа `int`:  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 Если значение, возвращаемое методом `Main`, не используется, то указание в качестве возвращаемого типа `void` несколько упрощает код. Однако возврат целого значения позволяет программе передавать информацию о своем состоянии другим программам и скриптам, которые вызывают исполняемый файл. В приведенном ниже примере показано, как получить доступ к значению, возвращаемому методом `Main`.  
  
## <a name="example"></a>Пример  
 В этом примере с помощью пакетного файла запускается программа, после чего проверяется значение, возвращаемое функцией `Main`. При запуске программы в Windows значение, возвращаемое функцией `Main`, сохраняется в переменной среды, которая называется `ERRORLEVEL`. Пакетный файл может определить результат выполнения посредством проверки значения переменной `ERRORLEVEL`. В большинстве случаев на успешное выполнение указывает нулевое значение. В приведенном ниже примере показана простая программа, в которой функция `Main` возвращает ноль. Нулевое значение указывает на успешное выполнение программы. Сохраните программу в файле MainReturnValTest.cs.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## <a name="example"></a>Пример  
 Так как в этом примере используется пакетный файл, рекомендуется выполнять компиляцию кода из командной строки. Выполните инструкции из раздела [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) для включения сборки из командной строки или воспользуйтесь командной строкой Visual Studio, которую можно открыть с помощью пункта **Инструменты Visual Studio** в меню **Пуск**. В командной строке перейдите в папку, в которой сохранена программа. С помощью показанной ниже команды выполняется компиляция файла MainReturnValTest.cs и создается исполняемый файл MainReturnValTest.exe.  
  
 `csc MainReturnValTest.cs`  
  
 Далее создайте пакетный файл для запуска файла MainReturnValTest.exe и вывода результата. Вставьте приведенный ниже код в текстовый файл и сохраните его под именем `test.bat` в папке, содержащей файлы MainReturnValTest.cs и MainReturnValTest.exe. Введите в командной строке команду `test`, чтобы запустить пакетный файл.  
  
 Так как код возвращает нулевое значение, пакетный файл сообщает об успехе. Однако если изменить файл MainReturnValTest.cs, чтобы он возвращал ненулевое значение, и затем перекомпилировать программу, при последующем выполнении пакетного файла будет выведено сообщение о неудаче.  
  
```  
rem test.bat  
@echo off  
MainReturnValTest  
@if "%ERRORLEVEL%" == "0" goto good  
  
:fail  
    echo Execution Failed  
    echo return value = %ERRORLEVEL%  
    goto end  
  
:good  
    echo Execution succeeded  
    echo Return value = %ERRORLEVEL%  
    goto end  
  
:end  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
