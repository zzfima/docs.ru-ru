---
title: "Аргументы командной строки (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 025ed2c451c0a657ce71db56df603302097fc7ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="command-line-arguments-c-programming-guide"></a>Аргументы командной строки (Руководство по программированию на C#)
Вы можете передавать аргументы в метод `Main`, определив метод одним из следующих способов:  
  
 [!code-csharp[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-csharp[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Чтобы включить аргументы командной строки в методе `Main` в приложении Windows Forms, необходимо вручную изменить сигнатуру `Main` в файле program.cs. Код, созданный с помощью конструктора Windows Forms, создает `Main` без входного параметра. Также можно использовать <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> или <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> для доступа к аргументам командной строки из любой точки в консоли или приложении Windows.  
  
 Параметр метода `Main` — это массив <xref:System.String>, представляющий аргументы командной строки. Как правило, определить, существуют ли аргументы, можно, проверив свойство `Length`, например:  
  
 [!code-csharp[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 Строковые аргументы также можно преобразовать в числовые типы с помощью класса <xref:System.Convert> или метода `Parse`. Например, следующая инструкция преобразует `string` в число `long` с помощью метода <xref:System.Int64.Parse%2A>:  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 Можно также использовать тип C# `long`, который является псевдонимом `Int64`:  
  
```  
long num = long.Parse(args[0]);  
```  
  
 Кроме того, можно использовать метод класса `Convert`, `ToInt64`:  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 Дополнительные сведения см. в разделах <xref:System.Int64.Parse%2A> и <xref:System.Convert>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование аргументов командной строки в консольном приложении. Приложение принимает один аргумент времени выполнения, преобразует аргумент в целое число и вычисляет факториал числа. Если не указано никаких аргументов, приложение выдает сообщение, поясняющее правильное использование программы.  
  
 Чтобы скомпилировать и запустить приложение из командной строки, выполните следующие действия.  
  
1.  Вставьте следующий код в любой текстовый редактор и сохраните файл как текстовый файл с именем `Factorial.cs`.  
  
     [!code-csharp[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  На **начальном** экране или в меню **Пуск** откройте окно **командной строки разработчика** Visual Studio и перейдите к папке, содержащей файл, который вы только что создали.  
  
3.  Введите следующую команду для компиляции приложения.  
  
     `csc Factorial.cs`  
  
     Если для приложения не выдаются ошибки компиляции, создается исполняемый файл с именем `Factorial.exe`.  
  
4.  Введите приведенную ниже команду для вычисления факториала числа 3:  
  
     `Factorial 3`  
  
5.  Код создает следующие выходные данные: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).  
  
 Дополнительные примеры об использовании командной строки см. в разделе [Практическое руководство. Создание и использование сборок с помощью командной строки](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Environment?displayProperty=nameWithType>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [Значения, возвращаемые методом main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
 [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)
