---
title: "Построение из командной строки с помощью csc.exe | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "построения [C#]"
  - "командная строка [C#]"
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Построение из командной строки с помощью csc.exe
Чтобы вызвать компилятор C#, следует ввести имя соответствующего исполняемого файла (csc.exe) в командной строке.  
  
 Если вы используете **командной строки Visual Studio** окна, все необходимые переменные среды устанавливаются автоматически. В Windows 7, то это окно можно открыть из **запустить** меню, откройте Microsoft Visual Studio *версии*папки \Visual Studio Tools. В Windows 8 Командная строка Visual Studio называется **командной строки разработчика для VS2012**, и его можно найти путем поиска на начальном экране.  
  
 Если используется стандартное окно командной строки, необходимо изменить путь к файлу csc.exe, прежде чем вызывать его из любого подкаталога на компьютере. Чтобы задать соответствующие переменные среды для поддержки построения из командной строки, необходимо запустить пакетный файл vsvars32.bat. Дополнительные сведения о файле vsvars32.bat, включая инструкции по найдите и запустите его, в разделе [Практическое руководство: задание переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Если вы работаете на компьютере, имеющем только [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong-md.md)], можно использовать компилятор C# **Командная строка пакета SDK**, которое можно открыть из **Microsoft .NET Framework SDK** пункт меню.  
  
 Для программного построения программ C# можно также использовать средство MSBuild. Дополнительные сведения см. в разделе [MSBuild](/visual-studio/msbuild/msbuild1).  
  
 Исполняемый файл csc.exe обычно находится в Microsoft.NET\Framework\\*версии* папку в каталоге Windows. Расположение файла может зависеть от конкретной конфигурации компьютера. Если на компьютере установлено несколько версий .NET Framework, будет несколько версий этого файла. Дополнительные сведения о подобных случаях установки см. в разделе [Определение которой версия .NET Framework установлена](http://msdn.microsoft.com/ru-ru/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c).  
  
> [!TIP]
>  При построении проекта с помощью Visual Studio IDE можно отобразить **csc** команды и ее связанные параметры компилятора в **вывода** окна. Для отображения этих сведений, следуйте инструкциям в [как: просмотр, сохранение и настройка файлов журнала построения](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md) изменить уровень детализации данных журнала для **Обычный** или **Подробные**. После сборки проекта выполните поиск **вывода** окно **csc** Найти вызова компилятора C#.  
  
 **В этом разделе**  
  
-   [Правила синтаксиса командной строки](#vcconcommand-linebuildinganchor1)  
  
-   [Примеры команд командной строки](#vcconcommand-linebuildinganchor2)  
  
-   [Различия между компилятор C# и выходные данные компилятора C++](#vcconcommand-linebuildinganchor3)  
  
##  <a name="a-namevcconcommand-linebuildinganchor1a-rules-for-command-line-syntax-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor1"></a> Правила синтаксиса командной строки для компилятора C#  
 Компилятор C# использует следующие правила при обработке аргументов, вводимых в командной строке операционной системы:  
  
-   Аргументы разделяются пробелами (пробел или табуляция).  
  
-   Символ каретки (^) не воспринимается как escape-символ или разделитель. Этот символ обрабатывается синтаксическим анализатором командной строки в операционной системе, прежде чем передается в массив argv программы.  
  
-   Строка, заключенная в двойные кавычки («строка»), интерпретируется как один аргумент, независимо от пробельных символов, содержащихся в. Строку в кавычках можно встроить в аргумент.  
  
-   Символ двойной кавычки после обратной косой (\\»), интерпретируется как символ двойной кавычки литерала ("«).  
  
-   Символы обратной косой черты обрабатываются буквально, если только им не предшествует двойная кавычка.  
  
-   Если четным числом символов обратной косой черты стоит двойная кавычка, один символ косой черты помещается в массив argv для каждой пары символов обратной косой черты и двойных кавычек, интерпретируется как разделитель строки.  
  
-   Если нечетного числа символов обратной косой черты стоит двойная кавычка, один символ косой черты помещается в массив argv для каждой пары символов обратной косой черты и двойных кавычек является «escape-последовательность оставшиеся обратную косую черту. В результате литеральный символ двойной кавычки ("") добавляется в argv.  
  
##  <a name="a-namevcconcommand-linebuildinganchor2a-sample-command-lines-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor2"></a> Примеры команд командной строки для компилятора C#  
  
-   Компилирует File.cs создания File.exe:  
  
    ```  
    csc File.cs   
    ```  
  
-   Компилирует создания файла File.dll File.cs:  
  
    ```  
    csc /target:library File.cs  
    ```  
  
-   Компилирует File.cs и создает My.exe:  
  
    ```  
    csc /out:My.exe File.cs  
    ```  
  
-   Компиляция всех файлов C# в текущем каталоге с оптимизацией на и определяет символ DEBUG. File2.exe выводится следующий результат:  
  
    ```  
    csc /define:DEBUG /optimize /out:File2.exe *.cs  
    ```  
  
-   Компиляция всех файлов C# в текущем каталоге, создание отладочной версии File2.dll. Логотипа и предупреждения не отображаются.  
  
    ```  
    csc /target:library /out:File2.dll /warn:0 /nologo /debug *.cs  
    ```  
  
-   Компиляция всех файлов C# в текущем каталоге в файл Something.xyz (DLL):  
  
    ```  
    csc /target:library /out:Something.xyz *.cs  
    ```  
  
##  <a name="a-namevcconcommand-linebuildinganchor3a-differences-between-c-compiler-and-c-compiler-output"></a><a name="vcconcommand-linebuildinganchor3"></a> Различия между компилятор C# и выходные данные компилятора C++  
 В результате вызова компилятора C# файлы объектов (OBJ-файлы) не создаются; выходные файлы создаются непосредственно. В результате компилятор C# не требуется средство связывания.  
  
## <a name="see-also"></a>См. также раздел  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [Параметры компилятора C#, упорядоченные по категориям](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [Практическое руководство: отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Практическое руководство: доступ аргументы командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Значения, возвращаемые методом Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)