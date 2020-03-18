---
title: Практическое руководство. Анализ путей к файлам
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: 6a959994be3a57795dc9f7e3447fa54bf075d3ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335348"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="e1b53-102">Практическое руководство. Анализ путей к файлам в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1b53-102">How to: Parse File Paths in Visual Basic</span></span>

<span data-ttu-id="e1b53-103">Объект <xref:Microsoft.VisualBasic.FileIO.FileSystem> предоставляет ряд полезных методов при анализе путей к файлам.</span><span class="sxs-lookup"><span data-stu-id="e1b53-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="e1b53-104">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> получает два пути и возвращает комбинированный путь в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="e1b53-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="e1b53-105">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> возвращает абсолютный путь к родительскому элементу указанного пути.</span><span class="sxs-lookup"><span data-stu-id="e1b53-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="e1b53-106">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> возвращает объект <xref:System.IO.FileInfo> , к которому можно выполнить запрос, чтобы определить свойства файла, например имя и путь.</span><span class="sxs-lookup"><span data-stu-id="e1b53-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="e1b53-107">По расширению файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="e1b53-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="e1b53-108">Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e1b53-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="e1b53-109">Определение имени и пути для файла</span><span class="sxs-lookup"><span data-stu-id="e1b53-109">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="e1b53-110">Используйте свойства <xref:System.IO.FileInfo.DirectoryName%2A> и <xref:System.IO.FileInfo.Name%2A> объекта <xref:System.IO.FileInfo> , чтобы определить для файла имя и путь.</span><span class="sxs-lookup"><span data-stu-id="e1b53-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="e1b53-111">В этом примере определяются и отображаются имя и путь.</span><span class="sxs-lookup"><span data-stu-id="e1b53-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="e1b53-112">Объединение имени и каталога файла для создания полного пути</span><span class="sxs-lookup"><span data-stu-id="e1b53-112">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="e1b53-113">Используйте метод `CombinePath` , указав каталог и имя.</span><span class="sxs-lookup"><span data-stu-id="e1b53-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="e1b53-114">В этом примере объединяются строки `folderPath` и `fileName` , созданные в предыдущем примере, и отображается результат.</span><span class="sxs-lookup"><span data-stu-id="e1b53-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="e1b53-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1b53-115">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="e1b53-116">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="e1b53-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
