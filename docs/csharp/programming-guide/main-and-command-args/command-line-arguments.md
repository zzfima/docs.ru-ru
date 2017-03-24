---
title: "Аргументы командной строки (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "аргументы командной строки [C#]"
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# Аргументы командной строки (Руководство по программированию на C#)
Можно отправлять аргументы методу `Main`, указав метод одним из следующих способов:  
  
 [!code-cs[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-cs[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Для включения аргументов командной строки в методе `Main` приложения Windows Forms, необходимо вручную изменить сигнатуру метода `Main` в program.cs.  Код, созданный конструктором Windows Forms, создает метод `Main` без входного параметра.  Для доступа к аргументам командной строки из любой точки на консоли или в приложении Windows можно использовать <xref:System.Environment.CommandLine%2A?displayProperty=fullName> or <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=fullName>.  
  
 Параметр метода `Main` является массивом значений типа <xref:System.String>, представляющим аргументы командной строки.  Обычно наличие аргументов определяется проверкой свойства `Length`, например:  
  
 [!code-cs[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 Кроме того, строковые аргументы можно преобразовать в числовые типы с помощью класса <xref:System.Convert> или метода `Parse`.  Например, следующая инструкция преобразует `string` в число типа `long` с помощью метода <xref:System.Int64.Parse%2A>:  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 Также можно использовать тип `long` языка C\#, являющийся псевдонимом типа `Int64`:  
  
```  
long num = long.Parse(args[0]);  
```  
  
 Для выполнения этой операции также можно воспользоваться методом `ToInt64` класса `Convert`:  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 Дополнительные сведения см. в разделах <xref:System.Int64.Parse%2A> и <xref:System.Convert>.  
  
## Пример  
 В следующем примере показано, как аргументы командной строки можно использовать в консольном приложении.  Приложение принимает аргументы по одному, преобразует каждый из них в целое число и вычисляет факториал этого числа.  Если ни одного аргумента не предоставлено, приложение выдает сообщение, содержащее разъяснение правильного использования данной программы.  
  
 Для компиляции и запуска приложения из командной строки выполните следующие действия.  
  
1.  Вставьте следующий код в любой текстовый редактор и сохраните его как текстовый файл с именем `Factorial.cs`.  
  
     [!code-cs[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  На экране **Пуск** или в меню **Пуск** откройте окно **Командная строка разработчика** Visual Studio, а затем перейдите в папку, содержащую созданный файл.  
  
3.  Введите следующую команду для компиляции приложения.  
  
     `csc Factorial.cs`  
  
     Если приложение не содержит ошибок компиляции, создается исполняемый файл с именем `Factorial.exe`.  
  
4.  Для вычисления факториала 3 введите следующую команду:  
  
     `Factorial 3`  
  
5.  Выходные результаты команды будут следующими: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio можно указать аргументы командной строки в [Страница "Отладка" в конструкторе проектов](/visual-studio/ide/reference/debug-page-project-designer).  
  
 Дополнительные примеры использования аргументов командной строки см. в разделе [Практическое руководство. Создание и использование сборок с помощью командной строки](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
## См. также  
 <xref:System.Environment?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Main\(\) и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Значения, возвращаемые методом Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)   
 [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)