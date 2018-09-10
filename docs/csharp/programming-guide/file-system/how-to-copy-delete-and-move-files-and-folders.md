---
title: Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: a9c5b1dc35878ac2e50a7c4ec72251885704fea6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858347"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)
В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>. В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс. Если нужно использовать стандартное диалоговое окна хода выполнения, см. раздел [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Используйте <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами. Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов. Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](../../../standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как копировать файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как перемещать файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как удалять файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO?displayProperty=nameWithType>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Файловая система и реестр (руководство по программированию на C#)](index.md)  
- [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
- [Файловый и потоковый ввод-вывод](../../../standard/io/index.md)  
- [Распространенные задачи ввода-вывода](../../../standard/io/common-i-o-tasks.md)
