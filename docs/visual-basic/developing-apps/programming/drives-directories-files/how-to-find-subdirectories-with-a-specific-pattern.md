---
title: "Практическое руководство. Поиск подкаталогов по шаблону в Visual Basic | Документы Майкрософт"
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
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: 16
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
ms.openlocfilehash: 3fc7683c6629e2d94f3acb670810c6632efec094
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a>Практическое руководство. Поиск подкаталогов по шаблону в Visual Basic
Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей к подкаталогам каталога. Для указания определенного шаблона можно использовать параметр `wildCards` . Если требуется включить в поиск содержимое подкаталогов, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.  
  
 Если каталоги, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a>Поиск подкаталогов по заданному шаблону  
  
-   Используйте метод `GetDirectories`, указав имя и путь к каталогу для поиска. В следующем примере возвращаются все каталоги в структуре каталогов, имена которых содержат слово "Logs". Затем они добавляются в `ListBox1`.  
  
     [!code-vb[VbVbcnFileAccess #1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Один или несколько указанных подстановочных знаков является `Nothing`, пустой строкой или содержит только пробелы (<xref:System.ArgumentNullException>).  
  
-   `directory` не существует (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` указывает на существующий файл (<xref:System.IO.IOException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
-   У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>   
 [Практическое руководство. Поиск файлов по конкретному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
