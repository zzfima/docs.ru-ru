---
title: "Файл слишком велик для чтения в массив байтов | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Файл слишком велик для чтения в массив байтов
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Размер файла, для которого предпринята попытка считывания в массив байтов превышает 4 ГБ.  Метод `My.Computer.FileSystem.ReadAllBytes` не может прочитать файл большего размера.  
  
### Чтобы исправить эту ошибку  
  
-   Для считывания файла используйте <xref:System.IO.StreamReader>.  Дополнительные сведения см. в разделе [Основы файлового ввода\-вывода и файловой системы в .NET Framework \(Visual Basic\)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:System.IO.StreamReader>   
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)   
 [Практическое руководство. Чтение текста из файлов с помощью StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)