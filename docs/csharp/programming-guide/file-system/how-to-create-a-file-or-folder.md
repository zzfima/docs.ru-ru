---
title: Практическое руководство. Руководство по программированию на C#. Создание файла или папки
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: c29d0638e2429119020fee5317d40a95b00e40ef
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590103"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Создание файла или папки
Вы можете программно создать на компьютере папку, вложенную папку и файл во вложенной папке, а затем записать данные в этот файл.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 Если папка уже существует, <xref:System.IO.Directory.CreateDirectory%2A> не выполняет никаких действий и исключение не возникает. Но <xref:System.IO.File.Create%2A?displayProperty=nameWithType> заменяет существующий файл новым. Для того чтобы этого избежать, в примере используется оператор `if`-`else`.  
  
 Изменив пример указанным ниже образом, вы можете задать различные результаты в зависимости от того, существует ли файл с определенным именем. Если файл не существует, он создается. Если файл существует, код добавляет в него данные.  
  
- Укажите конкретное имя файла.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- В следующем коде замените оператор `if`-`else` на `using`.  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 Выполните код в примере несколько раз, чтобы убедиться, что каждый раз данные добавляются в файл.  
  
 Другие значения `FileMode`, которые можно использовать для проверки, см. в разделе <xref:System.IO.FileMode>.  
  
 При следующих условиях возможно возникновение исключения:  
  
- Имя папки недопустимо, Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>). Используйте класс <xref:System.IO.Path>, чтобы создавать допустимые пути.  
  
- Родительская папка создаваемой папки доступна только для чтения (класс <xref:System.IO.IOException>).  
  
- Имя папки — `null` (класс <xref:System.ArgumentNullException>).  
  
- Имя папки слишком длинное (класс <xref:System.IO.PathTooLongException>).  
  
- Имя папки состоит из одного двоеточия ":" (класс <xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Экземпляр класса <xref:System.Security.SecurityException> может быть порожден как исключение в ситуации частичного доверия.  
  
 Если у вас нет разрешения на создание папки, код в приведенном примере породит как исключение экземпляр класса <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO?displayProperty=nameWithType>
- [Руководство по программированию на C#](../index.md)
- [Файловая система и реестр (руководство по программированию на C#)](./index.md)
