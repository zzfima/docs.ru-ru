---
title: "Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic | Документы Майкрософт"
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
- files, writing to
- text, writing to files
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
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
ms.openlocfilehash: 8478c97fe76582fba575aa6fbb7856cd37f4bbd3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a>Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic
Код в этом примере открывает объект <xref:System.IO.StreamWriter> с помощью метода `My.Computer.FileSystem.OpenTextFileWriter` и использует его для записи строки в текстовый файл с помощью метода <xref:System.IO.TextWriter.WriteLine%2A> класса <xref:System.IO.StreamWriter>.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).  
  
-   Диск переполнен (<xref:System.IO.IOException>).  
  
-   Слишком длинное имя пути (<xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 В этом примере создается файл (если файл отсутствует). Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`). Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии. Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamWriter>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 [Практическое руководство. Чтение из текстовых файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)   
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
