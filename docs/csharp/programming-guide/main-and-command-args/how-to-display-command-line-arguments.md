---
title: Как выполнить Руководство по программированию на C#. Отображение аргументов командной строки
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 948ff6e752b3f5cce870b483340cbbf9f4e78b01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607719"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Отображение аргументов командной строки
Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`. Аргументы предоставляются в форме массива строк. Каждый элемент массива содержит один аргумент. Пробелы между аргументами удаляются. Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:  
  
|Ввод в командной строке|Массив строк, передаваемых в метод Main|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"один два"<br /><br /> "три"|  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Пример  
 Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки. Показанные выходные данные — первая запись в таблице выше.  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)
- [Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [Значения, возвращаемые методом main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
