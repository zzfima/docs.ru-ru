---
title: "Практическое руководство. Получение сведений о файлах, папках и дисках (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 16950f835938846804ade1a8ad23d907aa69b9c3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)
В платформе .NET Framework доступ к сведениям о файловой системе можно получить, используя следующие классы:  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 Классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo> представляют файл или каталог, и содержат свойства, представляющие многие атрибуты файла, поддерживаемые файловой системой NTFS. Они также содержат методы для открытия, закрытия, перемещения и удаления файлов и папок. Экземпляры этих классов можно создать, передав в конструктор строку, представляющую имя файла, папки или диска.  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Имена файлов, папок или дисков можно также получить, используя вызовы <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> и <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.  
  
 Классы <xref:System.IO.Directory?displayProperty=fullName> и <xref:System.IO.File?displayProperty=fullName> предоставляют статические методы для поиска данных о каталогах и файлах.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы доступа к сведениям о файлах и папках.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При обработке заданных пользователем строк, определяющих пути, необходимо также обрабатывать исключения для следующих условий:  
  
-   Неверное имя файла. Например, оно содержит недопустимые символы или состоит из одних пробелов.  
  
-   Имя файла имеет значение NULL.  
  
-   Имя файла больше максимальной длины, определенной системой.  
  
-   Имя файла содержит двоеточие (:).  
  
 Если у приложения недостаточно прав для чтения указанного файла, метод `Exists` возвратит значение `false` независимо от существования указанного пути. Исключений этот метод не вызывает.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
