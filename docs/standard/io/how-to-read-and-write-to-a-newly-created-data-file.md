---
title: Практическое руководство. считывание данных из нового файла и запись в этот файл
ms.date: 01/21/2019
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
ms.openlocfilehash: 0bb06f42542d6acb3214fd4a1a3ca5c54f7caab2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706703"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Практическое руководство. считывание данных из нового файла и запись в этот файл
Классы <xref:System.IO.BinaryWriter?displayProperty=nameWithType> и <xref:System.IO.BinaryReader?displayProperty=nameWithType> используются для записи и чтения данных вместо строк символов. Следующий пример показывает, как создать пустой файловый поток, записать в него данные, а затем считать их. 

В этом примере создается файл данных *Test.data* в текущем каталоге, создаются связанные с ним объекты <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader>, а затем применяется объект <xref:System.IO.BinaryWriter> для записи целых чисел от 0 до 10 в *Test.data*. По завершении этих действий указатель файла остается в конце файла. Затем объект <xref:System.IO.BinaryReader> возвращает указатель файла в начало и считывает его содержимое.  
  
> [!NOTE]
> Если *Test.data* уже существует в текущем каталоге, создается исключение <xref:System.IO.IOException>. Используйте параметр файлового режима <xref:System.IO.FileMode.Create?displayProperty=nameWithType> вместо <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>, чтобы всегда создавать новый файл без появления исключения.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Практическое руководство. Чтение текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
