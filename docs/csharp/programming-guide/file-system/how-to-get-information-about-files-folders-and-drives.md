---
title: "Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "файлы [C#], получение сведений о"
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В платформе .NET Framework доступ к сведениям о файловой системе можно получить, используя следующие классы:  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 Классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo> представляют файл или каталог, и содержат свойства, представляющие многие атрибуты файла, поддерживаемые файловой системой NTFS.  Они также содержат методы для открытия, закрытия, перемещения и удаления файлов и папок.  Экземпляры этих классов можно создать, передав строку, представляющую в конструктор имя файла, папки или диска.  
  
```c#  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Имена файлов, папок или дисков можно также получить, используя вызовы <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> и <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.  
  
 Классы <xref:System.IO.Directory?displayProperty=fullName> и <xref:System.IO.File?displayProperty=fullName> предоставляют статические методы для поиска данных о каталогах и файлах.  
  
## Пример  
 В следующем примере показаны различные способы доступа к сведениям о файлах и папках.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## Отказоустойчивость  
 При обработке заданных пользователем строк, определяющих пути, необходимо также обрабатывать исключения для следующих условий:  
  
-   Неверное имя файла.  Например, оно содержит недопустимые символы или состоит из одних пробелов.  
  
-   Именем файла является NULL.  
  
-   Имя файла больше максимальной длины, определенной системой.  
  
-   Имя файла содержит двоеточие \(:\).  
  
 Если у приложения недостаточно прав для чтения указанного файла, метод `Exists` возвратит значение `false` независимо от существования указанного пути. Исключений этот метод не вызывает.  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)