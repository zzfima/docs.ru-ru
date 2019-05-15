---
title: Практическое руководство. Дозапись в текстовый файл в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
ms.openlocfilehash: e855293ac3636049520a85abdf685091d437bb60
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628910"
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a>Практическое руководство. Дозапись в текстовый файл в Visual Basic
Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> можно использовать для добавления данных в текстовый файл, задав для параметра `append` значение `True`.  
  
### <a name="to-append-to-a-text-file"></a>Добавление данных в текстовый файл  
  
- Используйте метод `WriteAllText`, указав конечный файл и строку, которую требуется добавить, и присвоив параметру `append` значение `True`.  
  
     В этом примере в файл с именем `Testfile.txt` записывается строка `"This is a test string."`.  
  
     [!code-vb[VbFileIOWrite#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#6)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
- `File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).  
  
- Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).  
  
- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
- Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
