---
title: "Доступ к файлам с помощью Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "данные [Visual Basic], доступ из файлам"
  - "доступ к файлам"
  - "доступ к файлам, использование компонентов"
  - "доступ к файлам, Visual Basic"
  - "файл классов ввода-вывода"
  - "файлы, доступ"
  - "файлы, Ввод и вывод"
  - "файлы, ввод и вывод"
  - "ввод-вывод [Visual Basic]"
  - "My.Computer.FileSystem - объект, доступ к файлам"
  - "последовательный доступ"
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Доступ к файлам с помощью Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект `My.Computer.FileSystem` предоставляет средства для работы с файлами и папками.  С помощью его свойств, методов и событий можно создавать, копировать, перемещать, собирать сведения и удалять файлы и папки.  `My.Computer.FileSystem` обеспечивает лучшую производительность, чем устаревшие функции \(`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` и т. д.\), оставленные в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для обеспечения обратной совместимости.  
  
## В этом подразделе  
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 Перечислены разделы, посвященные использованию объекта `My.Computer.FileSystem` для чтения файлов.  
  
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 Перечислены разделы, посвященные использованию объекта `My.Computer.FileSystem` для записи файлов.  
  
 [Создание, удаление и перемещение файлов и папок](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 Перечислены разделы, посвященные использованию объекта `My.Computer.FileSystem` для создания, копирования, удаления и перемещения файлов и папок.  
  
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 Описывается использование объекта `TextFieldReader` для разбора текстовых файлов, например журналов.  
  
 [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 Описываются кодировки файлов и их использование.  
  
 [Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 Описывается способ создания служебной программы, которая сообщает сведения о файлах и папках.  
  
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 Перечислены типичные проблемы при чтении и записи в текстовые файлы и предлагаются способы их устранения.