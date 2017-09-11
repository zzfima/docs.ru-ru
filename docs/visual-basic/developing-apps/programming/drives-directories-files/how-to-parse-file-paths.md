---
title: "Практическое руководство. Анализ путей к файлам в Visual Basic"
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
- file names, parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6327d661c6f1fe7647cc64b56d7f72f1f3455467
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="4f0cb-102">Практическое руководство. Анализ путей к файлам в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f0cb-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="4f0cb-103">Объект <xref:Microsoft.VisualBasic.FileIO.FileSystem> предоставляет ряд полезных методов при анализе путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
-   <span data-ttu-id="4f0cb-104">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> получает два пути и возвращает комбинированный путь в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
-   <span data-ttu-id="4f0cb-105">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> возвращает абсолютный путь к родительскому элементу указанного пути.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
-   <span data-ttu-id="4f0cb-106">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> возвращает объект <xref:System.IO.FileInfo> , к которому можно выполнить запрос, чтобы определить свойства файла, например имя и путь.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="4f0cb-107">По расширению файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="4f0cb-108">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="4f0cb-109">Определение имени и пути для файла</span><span class="sxs-lookup"><span data-stu-id="4f0cb-109">To determine a file's name and path</span></span>  
  
-   <span data-ttu-id="4f0cb-110">Используйте свойства <xref:System.IO.FileInfo.DirectoryName%2A> и <xref:System.IO.FileInfo.Name%2A> объекта <xref:System.IO.FileInfo> , чтобы определить для файла имя и путь.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="4f0cb-111">В этом примере определяются и отображаются имя и путь.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-111">This example determines the name and path and displays them.</span></span>  
  
     <span data-ttu-id="4f0cb-112">[!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f0cb-112">[!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]</span></span>  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="4f0cb-113">Объединение имени и каталога файла для создания полного пути</span><span class="sxs-lookup"><span data-stu-id="4f0cb-113">To combine a file's name and directory to create the full path</span></span>  
  
-   <span data-ttu-id="4f0cb-114">Используйте метод `CombinePath` , указав каталог и имя.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-114">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="4f0cb-115">В этом примере объединяются строки `folderPath` и `fileName` , созданные в предыдущем примере, и отображается результат.</span><span class="sxs-lookup"><span data-stu-id="4f0cb-115">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     <span data-ttu-id="4f0cb-116">[!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f0cb-116">[!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0cb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4f0cb-117">See Also</span></span>  
 <span data-ttu-id="4f0cb-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="4f0cb-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="4f0cb-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A></span><span class="sxs-lookup"><span data-stu-id="4f0cb-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A></span></span>   
 <span data-ttu-id="4f0cb-120"><xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="4f0cb-120"><xref:System.IO.FileInfo></span></span>   
 <span data-ttu-id="4f0cb-121"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A></span><span class="sxs-lookup"><span data-stu-id="4f0cb-121"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A></span></span>   
 [<span data-ttu-id="4f0cb-122">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="4f0cb-122">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

