---
title: Как выполнить Создание каталога в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: a7ba9ea1e7762b0a4a6660339c331fa6cdeb7858
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976906"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="3fb41-102">Как выполнить Создание каталога в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fb41-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="3fb41-103">Для создания каталога используйте метод `CreateDirectory` объекта `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="3fb41-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="3fb41-104">Если каталог уже существует, исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="3fb41-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="3fb41-105">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="3fb41-105">To create a directory</span></span>  
  
-   <span data-ttu-id="3fb41-106">Используйте метод `CreateDirectory`, указав полный путь к папке, где следует создать каталог.</span><span class="sxs-lookup"><span data-stu-id="3fb41-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="3fb41-107">В этом примере создается каталог `NewDirectory` в `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="3fb41-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3fb41-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="3fb41-108">Robust Programming</span></span>  
 <span data-ttu-id="3fb41-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="3fb41-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="3fb41-110">Неверное имя каталога.</span><span class="sxs-lookup"><span data-stu-id="3fb41-110">The directory name is malformed.</span></span> <span data-ttu-id="3fb41-111">Например, оно содержит недопустимые символы или состоит из одних пробелов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="3fb41-112">Родительский каталог создаваемого каталога доступен только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="3fb41-113">Именем каталога является `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="3fb41-114">Слишком длинное имя каталога (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="3fb41-115">Имя каталога состоит из двоеточия ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="3fb41-116">У пользователя нет разрешения на создание каталога (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="3fb41-117">У пользователя нет разрешений в ситуации частичного доверия (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="3fb41-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb41-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3fb41-118">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="3fb41-119">Создание, удаление и перемещение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="3fb41-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
