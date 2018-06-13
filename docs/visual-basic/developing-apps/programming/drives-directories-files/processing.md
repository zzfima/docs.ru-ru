---
title: Операции с дисками, папками и файлами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- drives
- drives, processing
- Visual Basic code, file access
- files [Visual Basic], processing
- files [Visual Basic], accessing
- directories [Visual Studio], processing
ms.assetid: f1db14c8-a4fd-4d0b-8323-c7cb29d688c2
ms.openlocfilehash: 0c9c1c787138595f725316a580acda9c5d4d43a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586758"
---
# <a name="processing-drives-directories-and-files-visual-basic"></a><span data-ttu-id="5d6e9-102">Операции с дисками, папками и файлами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6e9-102">Processing Drives, Directories, and Files (Visual Basic)</span></span>
<span data-ttu-id="5d6e9-103">Visual Basic можно использовать для обработки дисков, папок и файлов с помощью объекта `My.Computer.FileSystem`, который обеспечивает лучшую производительность и проще в использовании, чем традиционные методы, такие как `FileOpen` и `Write` (хотя они по-прежнему доступны).</span><span class="sxs-lookup"><span data-stu-id="5d6e9-103">You can use Visual Basic to process drives, folders, and files with the `My.Computer.FileSystem` object, which provides better performance and is easier to use than traditional methods such as the `FileOpen` and `Write` functions (although they are still available).</span></span> <span data-ttu-id="5d6e9-104">Эти методы подробно обсуждаются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-104">The following sections discuss these methods in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d6e9-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5d6e9-105">In This Section</span></span>  
 [<span data-ttu-id="5d6e9-106">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6e9-106">File Access with Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 <span data-ttu-id="5d6e9-107">Описание использования объекта `My.Computer.FileSystem` для работы с файлами, дисками и папками.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-107">Discusses how to use the `My.Computer.FileSystem` object to work with files, drives, and folders.</span></span>  
  
 [<span data-ttu-id="5d6e9-108">Основы файлового ввода-вывода и файловой системы в .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6e9-108">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)  
 <span data-ttu-id="5d6e9-109">Обзор концепций файлового ввода-вывода в .NET Framework, включая потоки, изолированное хранилище, события файла, атрибуты файла и доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-109">Provides an overview of file I/O concepts in the .NET Framework, including streams, isolated storage, file events, file attributes, and file access.</span></span>  
  
 [<span data-ttu-id="5d6e9-110">Пошаговое руководство. Управление файлами с помощью методов .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d6e9-110">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 <span data-ttu-id="5d6e9-111">Демонстрация использования [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для управления файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-111">Demonstrates how to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to manipulate files and folders.</span></span>  
  
 [<span data-ttu-id="5d6e9-112">Пошаговое руководство. Операции с файлами и каталогами в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6e9-112">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="5d6e9-113">Демонстрация использования объекта `My.Computer.FileSystem` для управления файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-113">Demonstrates how to use the `My.Computer.FileSystem` object to manipulate files and folders.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5d6e9-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5d6e9-114">Related Sections</span></span>  
 [<span data-ttu-id="5d6e9-115">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="5d6e9-115">Program Structure and Code Conventions</span></span>](../../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="5d6e9-116">Рекомендации по физической структуре и внешнему виду программ.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-116">Provides guidelines for the physical structure and appearance of programs.</span></span>  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <span data-ttu-id="5d6e9-117">Справочная документация по объекту `My.Computer.FileSystem` и его членам.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-117">Reference documentation for the `My.Computer.FileSystem` object and its members.</span></span>
