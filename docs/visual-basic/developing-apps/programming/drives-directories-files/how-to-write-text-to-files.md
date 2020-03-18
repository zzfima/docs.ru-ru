---
title: Практическое руководство. Запись текста в файлы
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: ce1ee59ba71af6bb13e05a5bce37a2f7eee37712
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334473"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a>Практическое руководство. Запись текста в файлы в Visual Basic

Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> можно использовать для записи текста в файлы. Если заданный файл не существует, он будет создан.  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-write-text-to-a-file"></a>Запись текста в файл  
  
- Используйте `WriteAllText` метод для записи текста в файл, указав файл и текст, который требуется записать. В этом примере строка `"This is new text."` записывается в файл с именем `test.txt`, при этом текст добавляется к тексту, имеющемуся в файле.  
  
     [!code-vb[VbFileIOWrite#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#3)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a>Запись набора строк в файл  
  
- Выполните цикл по коллекции строк. Используйте `WriteAllText` метод для записи текста в файл, указав конечный файл и строку, которую требуется добавить, и присвоив параметру `append` значение `True`.  
  
     В этом примере имена файлов в каталоге `Documents and Settings` записываются в файл `FileList.txt`, при этом между каждой записью вставляется символ перевода строки для удобства чтения.  
  
     [!code-vb[VbFileIOWrite#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#4)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
- `File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).  
  
- Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).  
  
- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
- Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
- Диск заполнен, и вызов `WriteAllText` завершается сбоем (<xref:System.IO.IOException>).  
  
 Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [Практическое руководство. Чтение из текстовых файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
