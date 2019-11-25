---
title: Практическое руководство. Копирование каталога в другой каталог
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: a23079f093f53ab8e20eb71c684a594dcf7f894b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348861"
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a>Практическое руководство. Копирование каталога в другой каталог в Visual Basic

Используйте метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> для копирования каталога в другой каталог. Этот метод копирует и содержимое каталога, и сам каталог. Если целевой каталог не существует, он будет создан. Если каталог с тем же именем уже существует в целевом расположении, а параметр `overwrite` имеет значение `False`, содержимое двух каталогов будут объединено. Во время операции можно указать новое имя для каталога.

При копировании файлов в каталоге могут возникать исключения, вызываемые определенным файлом, например файлом, существующим во время слияния, если параметр `overwrite` имеет значение `False`. Если такие исключения возникают, они объединяются в общее исключение. Свойство `Data` этого исключения содержит записи, в которых путь к файлу и каталогу является ключом, а соответствующее значение содержит сведения о конкретном исключении.

## <a name="to-copy-a-directory-to-another-directory"></a>Копирование каталога в другой каталог

- Воспользуйтесь методом `CopyDirectory`, указав имена исходного и целевого каталогов. Представленный в приведенном ниже примере код копирует каталог с именем `TestDirectory1` в `TestDirectory2`, перезаписывая существующие файлы.

    [!code-vb[VbVbcnMyFileSystem#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#16)]

    Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагментов кода он находится в разделе **Файловая система: обработка дисков, папок и файлов**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).

## <a name="robust-programming"></a>Отказоустойчивость

При следующих условиях возможно возникновение исключения:

- Новое имя, указанное для каталога, содержит двоеточие (:) или косую черту (\ или /) (<xref:System.ArgumentException>).

- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).

- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).

- Параметр `destinationDirectoryName` имеет значение `Nothing` или является пустой строкой (<xref:System.ArgumentNullException>).

- Целевой каталог не существует (<xref:System.IO.DirectoryNotFoundException>).

- Исходный каталог является корневым каталогом (<xref:System.IO.IOException>).

- Объединенный путь указывает на существующий файл (<xref:System.IO.IOException>).

- Исходный и конечный пути совпадают (<xref:System.IO.IOException>).

- `ShowUI` имеет значение `UIOption.AllDialogs`, а пользователь отменяет операцию, либо невозможно скопировать один или несколько файлов в каталоге (<xref:System.OperationCanceledException>).

- Операция является циклической (<xref:System.InvalidOperationException>).

- Путь содержит двоеточие (:) (<xref:System.NotSupportedException>).

- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).

- Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).

- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).

- Конечный файл существует, но недоступен (<xref:System.UnauthorizedAccessException>).

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>
- [Практическое руководство. Поиск подкаталогов по заданному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
