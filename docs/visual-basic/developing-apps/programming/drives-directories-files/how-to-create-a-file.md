---
title: "Практическое руководство. Создание файла в Visual Basic"
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
- text files, creating
- files, creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d06d274b31afad0a437405d1679e0be7548f2e14
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-in-visual-basic"></a>Практическое руководство. Создание файла в Visual Basic
В этом примере создается пустой текстовый файл по указанному пути с использованием метода <xref:System.IO.File.Create%2A> класса <xref:System.IO.File>.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для записи в файл используется переменная `file`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если файл уже существует, он заменяется.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Недопустимое имя пути Например, оно содержит недопустимые символы или состоит из одних пробелов (<xref:System.ArgumentException>).  
  
-   Путь доступен только для чтения (<xref:System.IO.IOException>).  
  
-   Имя пути — `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Имя пути слишком длинное (<xref:System.IO.PathTooLongException>).  
  
-   Указан недопустимый путь (<xref:System.IO.DirectoryNotFoundException>).  
  
-   Путь состоит только из двоеточия (":") (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Исключение <xref:System.Security.SecurityException> может быть создано в средах с частичным доверием.  
  
 Вызов метода <xref:System.IO.File.Create%2A> требует <xref:System.Security.Permissions.FileIOPermission>.  
  
 Исключение <xref:System.UnauthorizedAccessException> возникает, если пользователь не имеет разрешения на создание файла.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [Использование библиотек из не вполне надежного кода](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)   
 [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8)

