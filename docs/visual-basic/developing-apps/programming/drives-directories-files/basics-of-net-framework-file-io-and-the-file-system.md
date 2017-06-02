---
title: "Основы файлового ввода-вывода и файловой системы в .NET Framework (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file access, file I/O in Visual Basic
- file attributes, determining
- streams, fundamental operations
- file permissions
- streams
- streams, definition
ms.assetid: 49d837c0-cf28-416f-8606-4d83d7b479ef
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f471bac04a853e5876b9da52b7b858e1e1766e28
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="basics-of-net-framework-file-io-and-the-file-system-visual-basic"></a>Основы файлового ввода-вывода и файловой системы в .NET Framework (Visual Basic)
Классы в пространстве имен <xref:System.IO> используются для работы с дисками, файлами и каталогами.  
  
 Пространство имен <xref:System.IO> содержит классы <xref:System.IO.File> и <xref:System.IO.Directory>, обеспечивающие функциональные возможности [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] для работы с файлами и каталогами. Поскольку методы этих объектов являются статическими или общими элементами, их можно использовать непосредственно, без предварительного создания экземпляра класса. С этими классами связаны классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo>, которые будут знакомы пользователям функции `My`. Чтобы использовать эти классы, необходимо полностью уточнить имена или импортировать подходящие пространства имен, включив операторы `Imports` в начало соответствующего кода. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
> [!NOTE]
>  В других подразделах этого раздела для работы с дисками, файлами и каталогами вместо класса `My.Computer.FileSystem` используется объект `System.IO`. Объект `My.Computer.FileSystem` предназначен главным образом для использования в программах [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Классы `System.IO` предназначены для использования в любом языке, который поддерживает [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], в том числе [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="definition-of-a-stream"></a>Определение потока  
 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] использует потоки для поддержки чтения и записи файлов. Поток можно представить в виде одномерного набора связанных данных, у которого есть начало и конец, где курсор указывает текущее положение в потоке.  
  
 ![Курсор показывает текущую позицию в файловом потоке.](../../../../visual-basic/developing-apps/programming/drives-directories-files/media/filestream.gif "FileStream")  
  
## <a name="stream-operations"></a>Потоковые операции  
 Данные, содержащиеся в потоке, могут поступать из памяти, файла или сокета TCP/IP. Потоки имеют основные операции, которые могут быть применены к ним:  
  
-   Чтение. Вы можете выполнять чтение из потока, передавая данные в структуру данных, например строку или массив байтов.  
  
-   **Запись**. Вы можете выполнять запись в поток, передавая данные из источника данных в поток.  
  
-   **Поиск**. Вы можете запрашивать и изменять положение в потоке.  
  
 Для получения дополнительной информации см. [Composing Streams](https://msdn.microsoft.com/library/e4y2dch9).  
  
## <a name="types-of-streams"></a>Типы потоков  
 В [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] поток представлен классом <xref:System.IO.Stream>, который образует абстрактный класс для всех других потоков. Невозможно непосредственно создать экземпляр класса <xref:System.IO.Stream>, но необходимо использовать один из реализуемых им классов.  
  
 Существует много типов потоков, но при работе с файлами ввода-вывода наиболее важными типами являются класс <xref:System.IO.FileStream>, который предоставляет способ чтения и записи файлов, и класс <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>, который предоставляет способ создания файлов и каталогов в изолированном хранилище. К другим потокам, которые можно использовать при работе с файловым вводом-выводом, относятся следующие:  
  
-   <xref:System.IO.BufferedStream>  
  
-   <xref:System.Security.Cryptography.CryptoStream>  
  
-   <xref:System.IO.MemoryStream>  
  
-   <xref:System.Net.Sockets.NetworkStream>.  
  
 В следующей таблице перечислены типичные задачи, выполняемые с помощью потока:  
  
|Задача|См. статью|
|---|---|   
|Чтение и запись файла данных|[Практическое руководство. Считывание из нового файла данных и запись в этот файл](https://msdn.microsoft.com/library/36b93480.aspx)|  
|Чтение текста из файла|[Практическое руководство. Считывание текста из файла](https://msdn.microsoft.com/library/db5x7c0d.aspx)|  
|Запись текста в файл|[Практическое руководство. Запись текста в файл](https://msdn.microsoft.com/library/6ka1wd3w.aspx)|  
|Считывание символов из строки|[Практическое руководство. Считывание символов из строки](https://msdn.microsoft.com/library/9yyz8a6c.aspx)|  
|Запись символов в строку|[Практическое руководство. Запись символов в строку](https://msdn.microsoft.com/library/z4kzt0dd.aspx)|  
|Шифрование данных|[Шифрование данных](https://msdn.microsoft.com/library/as0w18af.aspx)|  
|Расшифровка данных|[Расшифровка данных](https://msdn.microsoft.com/library/te15te69.aspx)|  
  
## <a name="file-access-and-attributes"></a>Доступ к файлам и атрибуты  
 Вы можете управлять созданием, открытием файлов и их совместным использованием с перечислениями <xref:System.IO.FileAccess>, <xref:System.IO.FileMode> и <xref:System.IO.FileShare>, которые содержат флаги, используемые конструкторами класса <xref:System.IO.FileStream>. Например, когда вы открываете или создаете новый <xref:System.IO.FileStream>, перечисление <xref:System.IO.FileMode> позволяет указать, открывается ли файл для добавления, следует ли создать новый файл, если указанный файл не существует, будет ли перезаписан существующий файл и т. д.  
  
 Перечисление <xref:System.IO.FileAttributes> включает сбор относящихся к файлу сведений. Перечисление <xref:System.IO.FileAttributes> возвращает сохраненные атрибуты файла, например, является ли он сжатым, зашифрованным, скрытым, доступным только для чтения, архивом, каталогом, системным файлом или временным файлом.  
  
 В следующей таблице перечислены задачи, касающиеся доступа к файлам и атрибутов файлов:  
  
|Целевой тип|См.|  
|---|---|
|Открытие файла журнала и добавление в него текста|[Практическое руководство. Открытие файла журнала и добавление в него данных](https://msdn.microsoft.com/library/3zc0w663.aspx)|  
|Определение атрибутов файла|<xref:System.IO.FileAttributes>|  
  
## <a name="file-permissions"></a>Разрешения файла  
 Доступом к файлам и каталогам можно управлять с помощью класса <xref:System.Security.Permissions.FileIOPermission>. Это может быть особенно важно для разработчиков, работающих с веб-формами, которые по умолчанию выполняются в контексте специальной локальной учетной записи пользователя ASP.NET, создаваемой в рамках установок [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] и [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Когда такое приложение запрашивает доступ к ресурсу, учетная запись пользователя ASP.NET имеет ограниченные разрешения, что может помешать пользователю выполнять действия, такие как запись в файл из веб-приложения. Дополнительные сведения см. в статьях [о разрешениях безопасности](http://msdn.microsoft.com/en-us/b03757b4-e926-4196-b738-3733ced2bda0) и <xref:System.Security.Permissions.FileIOPermission>.  
  
## <a name="isolated-file-storage"></a>Изолированное хранилище файлов  
 Изолированное хранилище — это попытка устранить проблемы, которые могут возникать, если при работе с файлами у пользователя или кода отсутствуют необходимые разрешения. Изолированное хранилище назначает каждому пользователю секцию данных, которая может содержать одно или несколько хранилищ. Хранилища могут изолироваться друг от друга по пользователю или по сборке. Доступ к хранилищу имеет только пользователь и сборка, которые его создали. Хранилище действует в качестве полноценной виртуальной файловой системы — в пределах одного хранилища можно создавать и использовать каталоги и файлы.  
  
 В следующей таблице перечислены типичные задачи, связанные с изолированным хранилищем файлов.  
  
|Задача|См. статью|
|---|---|  
|Создание изолированного хранилища|[Практическое руководство. Получение хранилищ для изолированного хранения](https://msdn.microsoft.com/library/k48a6h13.aspx)|  
|Перечисление изолированных хранилищ|[Практическое руководство. Перечисление хранилищ для изолированного хранилища](https://msdn.microsoft.com/library/c3dy613a.aspx)|  
|Удаление изолированного хранилища|[Практическое руководство. Удаление хранилищ из области изолированного хранения](https://msdn.microsoft.com/library/5w71t104.aspx)|  
|Создание файла или каталога в изолированном хранилище|[Практическое руководство. Создание файлов и каталогов в изолированном хранилище](https://msdn.microsoft.com/library/6h2ws3ft.aspx)|  
|Поиск файла в изолированном хранилище|[Практическое руководство. Поиск существующих файлов и каталогов в изолированном хранилище](https://msdn.microsoft.com/library/zd5e2z84.aspx)|  
|Чтение или запись файла в изолированном хранилище|[Практическое руководство. Считывание из файлов и запись в файлы в изолированном хранилище](https://msdn.microsoft.com/library/xf96a1wz.aspx)|  
|Удаление файла или каталога в изолированном хранилище|[Практическое руководство. Удаление файлов и каталогов из изолированного хранилища](https://msdn.microsoft.com/library/kx3852wf.aspx)|  
  
## <a name="file-events"></a>События файлов  
 Компонент <xref:System.IO.FileSystemWatcher> позволяет наблюдать за изменениями в файлах и каталогах в локальной системе или на любом компьютере, к которому имеется доступ по сети. Например, при изменении файла можно отправить пользователю соответствующее оповещение. При внесении изменений выдается одно или несколько событий, которые сохраняются в буфере и передаются в компонент <xref:System.IO.FileSystemWatcher> для обработки.  
  
## <a name="see-also"></a>См. также  
 [Составление потоков](https://msdn.microsoft.com/library/e4y2dch9)   
 [Файловый и потоковый ввод-вывод](https://msdn.microsoft.com/library/k3352a4t)   
 [Асинхронный файловый ввод-вывод](https://msdn.microsoft.com/library/kztecsys)   
 [Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/classes-used-in-net-framework-file-io-and-the-file-system.md)
