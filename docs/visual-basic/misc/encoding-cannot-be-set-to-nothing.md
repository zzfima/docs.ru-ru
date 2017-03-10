---
title: "Параметру Encoding нельзя присвоить значение Nothing | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Параметру Encoding нельзя присвоить значение Nothing
Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing`, но требует допустимое значение.  
  
 <xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл. Кодировка по умолчанию — UTF\-8.  
  
### Исправление ошибки  
  
-   Предоставьте допустимое значение для параметра `encoding`.  
  
## См. также  
 [Кодировки файлов](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)   
 [Чтение из файлов](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Запись в файлы](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [Метод My.Computer.FileSystem.ReadAllText](http://msdn.microsoft.com/ru-ru/3a7ac8be-fb1d-4087-bc65-167d6754d57f)   
 [Метод My.Computer.FileSystem.WriteAllText](http://msdn.microsoft.com/ru-ru/f507460c-87d9-4504-b74f-3ff825c7d5c4)