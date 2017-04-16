---
title: "How to: Compile Conditionally with Trace and Debug | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "trace compiler options"
  - "trace statements"
  - "compiling source code, trace statements"
  - "tracing [.NET Framework], enabling or disabling"
  - "tracing [.NET Framework], compiling conditionally"
  - "TRACE directive"
  - "conditional compilation, tracing code"
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Compile Conditionally with Trace and Debug
При отладке приложения во время разработки выходные данные трассировки и отладки отображаются в окне «Вывод» Visual Studio.  Однако чтобы включить функции трассировки в развернутом приложении, необходимо скомпилировать инструментированные приложения с включенной директивой компилятора **TRACE**.  Это позволяет компилировать код трассировки в выпускаемой версии приложения.  Если не включить директиву **TRACE**, весь код трассировки игнорируется во время компиляции и не включается в исполняемый код, который будет развернут.  
  
 Методы трассировки и отладки имеют связанные условные атрибуты.  Например, если условный атрибут трассировки имеет значение **true**, все операторы трассировки включаются в сборку \(компилированные файлы .exe или .dll\); если условный атрибут **Trace** имеет значение **false**, операторы трассировки не включаются.  
  
 Для сборки можно включить условный атрибут **Trace** или **Debug**, оба эти атрибута одновременно или ни один из них.  Следовательно, существует четыре типа сборки: **Debug**, **Trace**, обе или ни одной.  Некоторые сборки выпуска для продуктивного развертывания могут не содержать ни одну из них, однако большинство сборок отладки содержат обе.  
  
 Можно задать параметры компилятора для вашего приложения несколькими способами.  
  
-   Страницы свойств  
  
-   Командная строка  
  
-   Оператор **\#CONST** \(для Visual Basic\) и **\#define** \(для C\#\)  
  
### Изменить параметры компиляции можно в диалоговом окне «Страницы свойств».  
  
1.  В **обозревателе решений** щелкните узел проекта правой кнопкой.  
  
2.  Выберите в контекстном меню команду **Свойства**.  
  
    -   В Visual Basic щелкните вкладку **Компиляция** в левой области страницы свойств, затем щелкните **Дополнительные параметры компиляции**, чтобы отобразить диалоговое окно **Дополнительные параметры компилятора**.  Установите флажки для параметров компилятора, которые необходимо включить.  Снимите флажки для параметров, которые необходимо отключить.  
  
    -   В C\# выберите **Построить** в левой области страницы свойств, а затем установите флажки для параметров компилятора, которые нужно включить.  Снимите флажки для параметров, которые необходимо отключить.  
  
### Компиляция инструментированного кода с помощью командной строки  
  
1.  Задайте условный параметр компилятора в командной строке.  Компилятор включит код трассировки или отладки в исполняемый файл.  
  
     Например, следующая инструкция компилятора, введенная в командной строке, включит код трассировки в компилируемый исполняемый файл.  
  
     Для Visual Basic: **vbc \/r:System.dll \/d:TRACE\=TRUE \/d:DEBUG\=FALSE MyApplication.vb**  
  
     Для C\#: **csc \/r:System.dll \/d:TRACE \/d:DEBUG\=FALSE MyApplication.cs**  
  
    > [!TIP]
    >  Чтобы скомпилировать несколько файлов приложений, оставьте пробел между именами файлов, например **MyApplication1.vb MyApplication2.vb MyApplication3.vb** или **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.  
  
     Директивы условной компиляции, используемые в приведенных выше примерах, имеют следующие значения.  
  
    |Директива|Значение|  
    |---------------|--------------|  
    |`vbc`|компилятор Visual Basic|  
    |`csc`|Компилятор C\#|  
    |`/r:`|Ссылка на внешнюю сборку \(EXE или DLL\)|  
    |`/d:`|Определяет символ условной компиляции|  
  
    > [!NOTE]
    >  Необходимо ввести команды TRACE или DEBUG буквами верхнего регистра.  Для получения дополнительных сведений о командах условной компиляции введите `vbc /?` \(для Visual Basic\) или `csc /?` \(для C\#\) в командной строке.  См. подробные сведения в статьях [Построение из командной строки](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md) \(C\#\) или [Вызов компилятора командной строки](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md) \(Visual Basic\).  
  
### Выполнение условной компиляции с помощью \#CONST или \#define  
  
1.  Введите соответствующую инструкцию для используемого языка программирования в верхней части файла исходного кода.  
  
    |Язык|Оператор|Результат|  
    |----------|--------------|---------------|  
    |**Visual Basic**|**\#CONST TRACE \= true**|Включает трассировку|  
    ||**\#CONST TRACE \= false**|Отключает трассировку|  
    ||**\#CONST DEBUG \= true**|Включает отладку|  
    ||**\#CONST DEBUG \= false**|Отключает отладку|  
    |**C\#**|**\#define TRACE**|Включает трассировку|  
    ||**\#undef TRACE**|Отключает трассировку|  
    ||**\#define DEBUG**|Включает отладку|  
    ||**\#undef DEBUG**|Отключает отладку|  
  
### Отключение трассировки или отладки  
  
1.  Удалите директиву компилятора из исходного кода.  
  
     \-или\-  
  
2.  Удалите комментарий к директиве компилятора.  
  
    > [!NOTE]
    >  Когда все готово для компиляции, можно выбрать команду **Построить** из меню **Сборка** или использовать метод командной строки \(но без ввода **d:**\), чтобы определить символы условной компиляции.  
  
## См. также  
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [How to: Add Trace Statements to Application Code](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [How to: Set Environment Variables for the Visual Studio Command Line](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md)   
 [Практическое руководство. Вызов компилятора командной строки](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md)