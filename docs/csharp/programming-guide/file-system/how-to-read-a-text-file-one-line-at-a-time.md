---
title: "Практическое руководство. Построчное чтение текстового файла (Visual C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "чтение текстовых файлов, построчно"
  - "ReadLine - метод [C#]"
  - "текстовые файлы [C#]"
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Построчное чтение текстового файла (Visual C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере производится построчное чтение содержимого текстового файла в строку с помощью метода `ReadLine` класса `StreamReader`.  Каждая строка текста сохраняется в строке `line` и отображается на экране.  
  
## Пример  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## Компиляция кода  
 Скопируйте код и вставьте его в метод `Main` консольного приложения.  
  
 Замените `"c:\test.txt"` фактическим именем файла.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Файл не существует.  
  
## Безопасность платформы .NET Framework  
 По имени файла не всегда можно с уверенностью судить о его содержимом.  Например, файл `myFile.cs` может не быть исходным файлом C\#.  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)