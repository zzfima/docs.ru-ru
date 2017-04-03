---
title: "Практическое руководство. Создание файла или папки (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
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
ms.openlocfilehash: bba53c8d175d95aa3b89ba458517d439a8d2bb11
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Практическое руководство. Создание файла или папки (Руководство по программированию на C#)
Вы можете программно создать на компьютере папку, вложенную папку и файл во вложенной папке, а затем записать данные в этот файл.  
  
## <a name="example"></a>Пример  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Если папка уже существует, <xref:System.IO.Directory.CreateDirectory%2A> ничего не делает и исключение не возникает. При этом <xref:System.IO.File.Create%2A?displayProperty=fullName> заменяет существующий файл на новый. Для того чтобы этого избежать, в примере используется оператор `if`-`else`.  
  
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
  
-   Имя папки недопустимо, например, содержит недопустимые символы или только пробелы (класс <xref:System.ArgumentException>). Для создания допустимых имен путей используйте класс <xref:System.IO.Path>.  
  
-   Родительская папка создаваемой папки доступна только для чтения (класс <xref:System.IO.IOException>).  
  
-   Имя папки имеет значение `null` (класс <xref:System.ArgumentNullException>).  
  
-   Слишком длинное имя папки (класс <xref:System.IO.PathTooLongException>).  
  
-   Имя папки содержит только двоеточие, ":" (класс <xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 В ситуациях частичного доверия может создаваться экземпляр класса <xref:System.Security.SecurityException>.  
  
 Если у вас нет разрешения на создание папки, код в приведенном примере создаст экземпляр класса <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
