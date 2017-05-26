---
title: "Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bb86918d68f40a2279a1a2729da33f9cd9e9e66e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic
Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей к файлам. Для указания определенного шаблона можно использовать параметр `wildCards` . Если требуется включить подкаталоги в поиск, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.  
  
 Если файлы, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.  
  
> [!NOTE]
>  Сведения о возврате списка файлов с помощью класса `DirectoryInfo` пространства имен `System.IO` см. в разделе <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>Поиск файлов по конкретному шаблону  
  
-   Используйте метод `GetFiles`, указав имя и путь к каталогу, в котором требуется выполнить поиск, и шаблон. В следующем примере возвращаются все файлы с расширением `.dll`, имеющиеся в каталоге, и добавляются в `ListBox1`.  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `directory` не существует (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` указывает на существующий файл (<xref:System.IO.IOException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
-   У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
