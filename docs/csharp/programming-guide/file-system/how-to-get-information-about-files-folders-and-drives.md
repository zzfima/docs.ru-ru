---
title: Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: c4f29cd2ae65fb05a2636ae3674c7ffd1613b0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338543"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)
В платформе .NET Framework доступ к сведениям о файловой системе можно получить, используя следующие классы:  
  
-   <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
-   <xref:System.IO.Directory?displayProperty=nameWithType>  
  
-   <xref:System.IO.File?displayProperty=nameWithType>  
  
 Классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo> представляют файл или каталог и содержат свойства, представляющие многие атрибуты файла, поддерживаемые файловой системой NTFS. Они также содержат методы для открытия, закрытия, перемещения и удаления файлов и папок. Экземпляры этих классов можно создать, передав в конструктор строку, представляющую имя файла, папки или диска.  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Имена файлов, папок или дисков можно также получить с помощью вызова <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> и <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.  
  
 Классы <xref:System.IO.Directory?displayProperty=nameWithType> и <xref:System.IO.File?displayProperty=nameWithType> предоставляют статические методы для получения сведений о каталогах и файлах.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы доступа к сведениям о файлах и папках.  
  
 [!code-csharp[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При обработке заданных пользователем строк, определяющих пути, необходимо также обрабатывать исключения для следующих условий:  
  
-   Неверное имя файла. Например, оно содержит недопустимые символы или состоит из одних пробелов.  
  
-   Имя файла имеет значение NULL.  
  
-   Имя файла больше максимальной длины, определенной системой.  
  
-   Имя файла содержит двоеточие (:).  
  
 Если у приложения недостаточно прав для чтения указанного файла, метод `Exists` возвратит значение `false` независимо от существования указанного пути. Исключений этот метод не вызывает.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO?displayProperty=nameWithType>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
