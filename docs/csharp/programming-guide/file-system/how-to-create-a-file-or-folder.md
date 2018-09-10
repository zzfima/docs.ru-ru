---
title: Практическое руководство. Создание файла или папки (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 34919efe32730fe0db11cb881b8e07629a3094fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207464"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Практическое руководство. Создание файла или папки (Руководство по программированию на C#)
Вы можете программно создать на компьютере папку, вложенную папку и файл во вложенной папке, а затем записать данные в этот файл.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Если папка уже существует, <xref:System.IO.Directory.CreateDirectory%2A> не выполняет никаких действий и исключение не возникает. Но <xref:System.IO.File.Create%2A?displayProperty=nameWithType> заменяет существующий файл новым. Для того чтобы этого избежать, в примере используется оператор `if`-`else`.  
  
 Изменив пример указанным ниже образом, вы можете задать различные результаты в зависимости от того, существует ли файл с определенным именем. Если файл не существует, он создается. Если файл существует, код добавляет в него данные.  
  
-   Укажите конкретное имя файла.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   В следующем коде замените оператор `if`-`else` на `using`.  
  
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
  
-   Имя папки недопустимо, Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>). Используйте класс <xref:System.IO.Path>, чтобы создавать допустимые пути.  
  
-   Родительская папка создаваемой папки доступна только для чтения (класс <xref:System.IO.IOException>).  
  
-   Имя папки — `null` (класс <xref:System.ArgumentNullException>).  
  
-   Имя папки слишком длинное (класс <xref:System.IO.PathTooLongException>).  
  
-   Имя папки состоит из одного двоеточия ":" (класс <xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Экземпляр класса <xref:System.Security.SecurityException> может быть порожден как исключение в ситуации частичного доверия.  
  
 Если у вас нет разрешения на создание папки, код в приведенном примере породит как исключение экземпляр класса <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO?displayProperty=nameWithType>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
