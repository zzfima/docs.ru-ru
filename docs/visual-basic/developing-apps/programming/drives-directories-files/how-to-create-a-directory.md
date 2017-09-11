---
title: "Практическое руководство. Создание каталога в Visual Basic"
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
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a45a785916b480dcee6e36fd295390266eaa0a0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="ddeaf-102">Практическое руководство. Создание каталога в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddeaf-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="ddeaf-103">Для создания каталога используйте метод `CreateDirectory` объекта `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="ddeaf-104">Если каталог уже существует, исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="ddeaf-105">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="ddeaf-105">To create a directory</span></span>  
  
-   <span data-ttu-id="ddeaf-106">Используйте метод `CreateDirectory`, указав полный путь к папке, где следует создать каталог.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="ddeaf-107">В этом примере создается каталог `NewDirectory` в `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     <span data-ttu-id="ddeaf-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ddeaf-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ddeaf-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ddeaf-109">Robust Programming</span></span>  
 <span data-ttu-id="ddeaf-110">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="ddeaf-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ddeaf-111">Неверное имя каталога.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-111">The directory name is malformed.</span></span> <span data-ttu-id="ddeaf-112">Например, оно содержит недопустимые символы или состоит из одних пробелов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-113">Родительский каталог создаваемого каталога доступен только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-114">Именем каталога является `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-115">Слишком длинное имя каталога (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-116">Имя каталога состоит из двоеточия ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-117">У пользователя нет разрешения на создание каталога (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="ddeaf-118">У пользователя нет разрешений в ситуации частичного доверия (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="ddeaf-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeaf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ddeaf-119">See Also</span></span>  
 <span data-ttu-id="ddeaf-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="ddeaf-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span></span>   
 [<span data-ttu-id="ddeaf-121">Создание, удаление и перемещение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="ddeaf-121">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)

