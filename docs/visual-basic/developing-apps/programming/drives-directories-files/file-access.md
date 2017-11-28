---
title: "Доступ к файлам с помощью Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9929061feeccee31028056bc93f0f0a2f119eb4e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="9b228-102">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b228-102">File Access with Visual Basic</span></span>
<span data-ttu-id="9b228-103">Объект `My.Computer.FileSystem` предоставляет средства для работы с файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="9b228-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="9b228-104">Его свойства, методы и события позволяют создавать, копировать, перемещать, исследовать и удалять файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="9b228-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="9b228-105">`My.Computer.FileSystem` обеспечивает более высокую производительность, чем устаревшие функции (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` и т. д.), предоставляемые [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="9b228-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b228-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="9b228-106">In This Section</span></span>  
 [<span data-ttu-id="9b228-107">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="9b228-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="9b228-108">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для чтения из файлов.</span><span class="sxs-lookup"><span data-stu-id="9b228-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="9b228-109">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="9b228-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="9b228-110">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для записи в файлы.</span><span class="sxs-lookup"><span data-stu-id="9b228-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="9b228-111">Создание, удаление и перемещение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="9b228-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="9b228-112">Список разделов, посвященных использованию объекта `My.Computer.FileSystem` для создания, копирования, удаления и перемещения файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="9b228-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="9b228-113">Анализ текстовых файлов с помощью объекта TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="9b228-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="9b228-114">Описание использования объекта `TextFieldReader` для анализа таких текстовых файлов как журналов.</span><span class="sxs-lookup"><span data-stu-id="9b228-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="9b228-115">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="9b228-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="9b228-116">Описание кодировок файлов и их применения.</span><span class="sxs-lookup"><span data-stu-id="9b228-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="9b228-117">Пошаговое руководство. Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b228-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="9b228-118">Демонстрация создания служебной программы, сообщающей сведения о файлах и папках.</span><span class="sxs-lookup"><span data-stu-id="9b228-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="9b228-119">Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы</span><span class="sxs-lookup"><span data-stu-id="9b228-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="9b228-120">Список распространенных проблем, возникающих при чтении и записи в текстовые файлы, и предлагаемые способы их устранения.</span><span class="sxs-lookup"><span data-stu-id="9b228-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
