---
title: Доступ к файлам
ms.date: 07/20/2015
helpviewer_keywords:
- file access
- files [Visual Basic], input and output
- file access, Visual Basic
- files [Visual Basic], I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files [Visual Basic], accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
ms.openlocfilehash: 22bcd0f1f3acb0c0ad899b83ad2d879ead948f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348899"
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="06ba5-102">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06ba5-102">File Access with Visual Basic</span></span>

<span data-ttu-id="06ba5-103">Объект `My.Computer.FileSystem` предоставляет средства для работы с файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="06ba5-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="06ba5-104">Его свойства, методы и события позволяют создавать, копировать, перемещать, исследовать и удалять файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="06ba5-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="06ba5-105">`My.Computer.FileSystem` обеспечивает более высокую производительность, чем устаревшие функции (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` и т. д.), предоставляемые Visual Basic для поддержки обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="06ba5-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by Visual Basic for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06ba5-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="06ba5-106">In This Section</span></span>  

 [<span data-ttu-id="06ba5-107">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="06ba5-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="06ba5-108">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для чтения из файлов.</span><span class="sxs-lookup"><span data-stu-id="06ba5-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="06ba5-109">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="06ba5-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="06ba5-110">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для записи в файлы.</span><span class="sxs-lookup"><span data-stu-id="06ba5-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="06ba5-111">Создание, удаление и перемещение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="06ba5-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="06ba5-112">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для создания, копирования, удаления и перемещения файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="06ba5-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="06ba5-113">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="06ba5-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="06ba5-114">Описание использования объекта `TextFieldReader` для анализа таких текстовых файлов как журналов.</span><span class="sxs-lookup"><span data-stu-id="06ba5-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="06ba5-115">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="06ba5-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="06ba5-116">Описание кодировок файлов и их применения.</span><span class="sxs-lookup"><span data-stu-id="06ba5-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="06ba5-117">Пошаговое руководство. Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06ba5-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="06ba5-118">Демонстрация создания служебной программы, сообщающей сведения о файлах и папках.</span><span class="sxs-lookup"><span data-stu-id="06ba5-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="06ba5-119">Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы</span><span class="sxs-lookup"><span data-stu-id="06ba5-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="06ba5-120">Список распространенных проблем, возникающих при чтении и записи в текстовые файлы, и предлагаемые способы их устранения.</span><span class="sxs-lookup"><span data-stu-id="06ba5-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
