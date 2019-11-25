---
title: Практическое руководство. Поиск файлов по конкретному шаблону
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 5faaa16615f52714db3de6853786990265716501
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348760"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic

Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей для файлов. Для указания определенного шаблона можно использовать параметр `wildCards` . Если требуется включить подкаталоги в поиск, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.  
  
 Если файлы, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.  
  
> [!NOTE]
> Сведения о возврате списка файлов с помощью класса `DirectoryInfo` пространства имен `System.IO` см. в разделе <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>Поиск файлов по конкретному шаблону  
  
- Используйте метод `GetFiles`, указав имя и путь к каталогу, в котором требуется выполнить поиск, и шаблон. В следующем примере возвращаются все файлы с расширением `.dll`, имеющиеся в каталоге, и добавляются в `ListBox1`.  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  

 При следующих условиях возможно возникновение исключения:  
  
- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
- `directory` не существует (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` указывает на существующий файл (<xref:System.IO.IOException>).  
  
- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
- Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
- У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Практическое руководство. Поиск подкаталогов по заданному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
