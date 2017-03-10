---
title: "Практическое руководство. Создание файла или папки (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "создание файлов [C#]"
  - "создание папок [C#]"
  - "файлы [C#]"
  - "папки [C#]"
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Практическое руководство. Создание файла или папки (Руководство по программированию на C#)
Можно программно создать папку на компьютере, создать вложенную папку, создать файл во вложенной папке и записать данные в этот файл.  
  
## Пример  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#10)]  
  
 Если папка уже существует, метод <xref:System.IO.Directory.CreateDirectory%2A> ничего не делает и исключение не возникает.  Однако <xref:System.IO.File.Create%2A?displayProperty=fullName> заменяет существующий файл новым файлом.  В этом примере используется оператор `if`\-`else` для предотвращения замены существующего файла.  
  
 Внесение следующих изменений в примере позволяет задать различные результаты в зависимости от того, существует ли уже файл с определенным именем.  Если такого файла не существует, код создает его.  Если такой файл существует, код добавляет данные в этот файл.  
  
-   Укажите непроизвольное имя файла.  
  
    ```c#  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   Замените инструкцию `if`\-`else` инструкцией `using` в следующем коде.  
  
    ```c#  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 Запустите образец несколько раз, чтобы убедиться, что данные добавляются в файл каждый раз.  
  
 Другие значения `FileMode`, которые можно попробовать, см. в разделе <xref:System.IO.FileMode>.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Неверное имя папки.  Например, в нем содержатся недопустимые знаки, или имя состоит из одних пробелов \(класс <xref:System.ArgumentException>\).  Используйте класс <xref:System.IO.Path> для создания допустимых имен путей.  
  
-   Родительская папка или создаваемая папка доступна только для чтения \(класс <xref:System.IO.IOException>\).  
  
-   Именем папки является `null` \(класс <xref:System.ArgumentNullException>\).  
  
-   Имя папки имеет слишком большую длину \(класс <xref:System.IO.PathTooLongException>\).  
  
-   В имени папки присутствует только двоеточие, ":" \(класс <xref:System.IO.PathTooLongException>\).  
  
## Безопасность платформы .NET Framework  
 Экземпляр класса <xref:System.Security.SecurityException> может появляться в ситуациях частичного доверия.  
  
 Если пользователь не имеет разрешения для создания папки, в примере возникает экземпляр класса <xref:System.UnauthorizedAccessException>.  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)