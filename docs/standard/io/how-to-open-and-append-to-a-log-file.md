---
title: Практическое руководство. открытие файла журнала и добавление в него данных
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: b0e399ba3c0cfa0ad3b92afbc7e07af7659e8ae6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706716"
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Практическое руководство. открытие файла журнала и добавление в него данных
<xref:System.IO.StreamWriter> и <xref:System.IO.StreamReader> записывают данные в потоки и считывают данные из потоков. Следующий пример кода открывает файл *log.txt* для получения входных данных или создает его, если он не существует, а затем добавляет сведения журнала в конец файла. После этого он записывает содержимое файла для отображения в стандартный поток вывода. 

Вместо использованного здесь подхода вы можете сохранить сведения в одной строке или в массиве строк и выполнить те же функции с помощью метода <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> или <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> Пользователи Visual Basic могут использовать методы и свойства, предоставляемые классом <xref:Microsoft.VisualBasic.Logging.Log> или <xref:Microsoft.VisualBasic.FileIO.FileSystem>, для создания файлов журнала и записи данных в них.  
  
## <a name="example"></a>Пример  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Практическое руководство. Считывание данных из нового файла и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Практическое руководство. Чтение текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
