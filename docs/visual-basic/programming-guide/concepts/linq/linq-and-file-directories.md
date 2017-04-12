---
title: "LINQ и каталоги файлов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5536ae95b42cdaddda2c4cae97a114681e94b0ab
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ и каталоги файлов (Visual Basic)
Многие операции файловой системы, по существу запросов и, следовательно, хорошо подходит для подход LINQ.  
  
 Обратите внимание, что запросы в этом разделе являются безопасными. Они не используются для изменения содержимого исходных файлов или папок. Эта процедура выполняется правило, запросы не должны вызывать никаких побочных эффектов. Как правило любой код (включая запросы, выполняющие создания, обновления и удаления операторов), изменяющий исходные данные должны храниться отдельно от кода, который просто запрашивает данные.  
  
 В этом разделе рассматриваются следующие вопросы.  
  
 [Практическое руководство: запрос файлов с указанными атрибутами или именем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 Описание способов поиска файлов путем проверки одного или нескольких свойств его <xref:System.IO.FileInfo>объекта.</xref:System.IO.FileInfo>  
  
 [Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 Описание способов возврата групп <xref:System.IO.FileInfo>объекта в зависимости от расширения имени файла.</xref:System.IO.FileInfo>  
  
 [Практическое руководство: запрос общее количество байтов в наборе папок (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 Показано, как вернуть общее число байтов во всех файлах в указанном дереве каталогов.  
  
 [Практическое руководство: сравнение содержимого двух папок (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s  
 Показано, как вернуть все файлы, присутствующие в двух указанных папках, а также все файлы, которые присутствуют в одной папке, но отсутствующих в другой.  
  
 [Практическое руководство: запрос самого большого файла или файлов в дереве каталогов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 Описание способов возврата наибольшего или наименьшего файла или определенного числа файлов, в дереве каталогов.  
  
 [Практическое руководство: запрос повторяющихся файлов в дереве каталогов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 Описание способов группировки всех имен файлов, находящихся в нескольких местах в указанном дереве каталогов. Также показано, как для выполнения более сложных сравнений с учетом пользовательского блока сравнения.  
  
 [Практическое руководство: запрос содержимого файлов в папке (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 Показано, как перебора папок в дереве, открытия каждого файла и запроса к содержимому файла.  
  
## <a name="comments"></a>Комментарии  
 Существует некоторые сложности, связанные с созданием источника данных, который точно представляет содержимое файловой системы и корректно обрабатывает исключения. В примерах этого раздела создается моментальный снимок коллекции из <xref:System.IO.FileInfo>объектов, представляющих все файлы в указанной корневой папке и всех ее подпапках.</xref:System.IO.FileInfo> Фактическое состояние каждого <xref:System.IO.FileInfo>может измениться в период между началом и окончанием выполнения запроса.</xref:System.IO.FileInfo> Например, можно создать список <xref:System.IO.FileInfo>объектов для использования в качестве источника данных.</xref:System.IO.FileInfo> Если при попытке доступа к `Length` свойства в запросе, <xref:System.IO.FileInfo>объекта попытается получить доступ к файловой системе для обновления значения `Length`.</xref:System.IO.FileInfo> Если файл больше не существует, вы получите <xref:System.IO.FileNotFoundException>в запросе, даже если вы не выполняется в файловой системе непосредственный запрос.</xref:System.IO.FileNotFoundException> Некоторые запросы в этом разделе используют отдельный метод, который использует эти конкретные исключения в определенных случаях. Другой возможностью является поддержка источника данных обновленным динамически с помощью <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher>  
  
## <a name="see-also"></a>См. также  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
