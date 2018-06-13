---
title: Практическое руководство. Считывание из нового файла данных и запись в этот файл
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b854495a32755b2cbbd0421b1a45458fd2b7863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572701"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Практическое руководство. Считывание из нового файла данных и запись в этот файл
Классы <xref:System.IO.BinaryWriter> И <xref:System.IO.BinaryReader?displayProperty=nameWithType> используются для записи и чтения данных вместо строк символов. Следующий пример демонстрирует запись данных в новый пустой файловый поток с именем `Test.data` и чтение данных из него. Этот код создает файл данных в текущем каталоге, создает связанные с ним объекты <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader>, а затем применяет объект <xref:System.IO.BinaryWriter> для записи в `Test.data` целых чисел с 0 до 10. По завершении этих действий указатель файла остается в конце файла. Затем пример кода возвращает указатель файла в начало и через объект <xref:System.IO.BinaryReader> считывает его содержимое.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если `Test.data` уже существует в текущем каталоге, создается исключение <xref:System.IO.IOException>. Используйте параметр <xref:System.IO.FileMode.Create?displayProperty=nameWithType> файлового режима при инициализации файлового потока, чтобы всегда создавать новый файл без появления исключения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
