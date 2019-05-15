---
title: Практическое руководство. Создание файла в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: f24fdd6ce1fea7540c33e4a2fdfc06885825f76a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628986"
---
# <a name="how-to-create-a-file-in-visual-basic"></a>Практическое руководство. Создание файла в Visual Basic
В этом примере создается пустой текстовый файл по указанному пути с использованием метода <xref:System.IO.File.Create%2A> класса <xref:System.IO.File>.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для записи в файл используется переменная `file`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если файл уже существует, он заменяется.  
  
 При следующих условиях возможно возникновение исключения:  
  
- Недопустимое имя пути Например, оно содержит недопустимые символы или состоит из одних пробелов (<xref:System.ArgumentException>).  
  
- Путь доступен только для чтения (<xref:System.IO.IOException>).  
  
- Имя пути — `Nothing` (<xref:System.ArgumentNullException>).  
  
- Имя пути слишком длинное (<xref:System.IO.PathTooLongException>).  
  
- Указан недопустимый путь (<xref:System.IO.DirectoryNotFoundException>).  
  
- Путь состоит только из двоеточия (":") (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Исключение <xref:System.Security.SecurityException> может быть создано в средах с частичным доверием.  
  
 Вызов метода <xref:System.IO.File.Create%2A> требует <xref:System.Security.Permissions.FileIOPermission>.  
  
 Исключение <xref:System.UnauthorizedAccessException> возникает, если пользователь не имеет разрешения на создание файла.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [Использование библиотек из частично доверенного кода](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md)
