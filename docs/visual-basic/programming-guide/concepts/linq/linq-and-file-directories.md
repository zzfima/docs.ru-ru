---
title: LINQ и каталоги файлов
ms.date: 07/20/2015
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
ms.openlocfilehash: 390d3c7a1c738aea0df8e3dcad0edb70563f8fb6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347791"
---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ and File Directories (Visual Basic)
Многие операции файловой системы по существу являются запросами и, следовательно, соответствуют принципам LINQ.  
  
 Обратите внимание, что запросы в этом разделе являются безопасными. Они не используются для изменения содержимого исходных файлов или папок. Это соответствует правилу о том, что запросы не должны вызывать никаких побочных эффектов. Как правило, любой код (включая запросы, выполняющие операторы создания, изменения и удаления), изменяющий исходные данные, должен храниться отдельно от кода, который просто запрашивает данные.  
  
 В этом разделе рассматриваются следующие вопросы.  
  
 [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 Демонстрация поиска файлов путем проверки одного или нескольких свойств его объекта <xref:System.IO.FileInfo>.  
  
 [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 Демонстрация возвращения групп объектов <xref:System.IO.FileInfo> в зависимости от расширения имени файла.  
  
 [How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 Демонстрация возвращения общего числа байтов во всех файлах в указанном дереве каталогов.  
  
 [How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s  
 Демонстрация возвращения всех файлов, присутствующих в двух указанных папках, а также всех файлов, которые присутствуют в одной папке, но отсутствуют в другой.  
  
 [How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 Демонстрация возвращения наибольшего или наименьшего файла либо определенного числа файлов в дереве каталогов.  
  
 [How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 Демонстрация группирования всех имен файлов, находящихся в нескольких расположениях в указанном дереве каталогов. Также показано, как выполнять более сложные сравнения на основе пользовательской функции сравнения.  
  
 [How to query the contents of files in a folder (LINQ) (Visual Basic)](how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 Демонстрация итерации по папкам в дереве, открытия каждого файла и запроса содержимого файла.  
  
## <a name="comments"></a>Комментарии  
 Существуют некоторые сложности, связанные с созданием источника данных, который точно представляет содержимое файловой системы и корректно обрабатывает исключения. В примерах этого раздела создается моментальный снимок коллекции объектов <xref:System.IO.FileInfo>, представляющих все файлы в указанной корневой папке и всех ее подпапках. Фактическое состояние каждого объекта <xref:System.IO.FileInfo> может измениться в период между началом и окончанием выполнения запроса. Например, можно создать список объектов <xref:System.IO.FileInfo> для использования в качестве источника данных. При попытке доступа к свойству `Length` в запросе объект <xref:System.IO.FileInfo> попытается получить доступ к файловой системе для обновления значения `Length`. Если файл больше не существует, вы получите исключение <xref:System.IO.FileNotFoundException> в запросе, даже если не запрашиваете файловую систему напрямую. Некоторые запросы в этом разделе используют отдельный метод, который использует эти конкретные исключения в определенных случаях. Другой возможностью является поддержка источника данных, обновляемого динамически с помощью <xref:System.IO.FileSystemWatcher>.  
  
## <a name="see-also"></a>См. также

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
