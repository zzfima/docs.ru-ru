---
title: "Недопустимое имя файла или номер"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="de5e5-102">Недопустимое имя файла или номер</span><span class="sxs-lookup"><span data-stu-id="de5e5-102">Bad file name or number</span></span>
<span data-ttu-id="de5e5-103">Произошла ошибка при попытке доступа к указанному файлу.</span><span class="sxs-lookup"><span data-stu-id="de5e5-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="de5e5-104">Среди возможных причин этой ошибки являются:</span><span class="sxs-lookup"><span data-stu-id="de5e5-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="de5e5-105">Инструкция ссылается на файл с именем файла или номер, который не был указан в `FileOpen` инструкции или был указан в `FileOpen` инструкции однако впоследствии был закрыт.</span><span class="sxs-lookup"><span data-stu-id="de5e5-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="de5e5-106">Инструкция ссылается на файл с номером, который находится за пределами диапазона номеров файлов.</span><span class="sxs-lookup"><span data-stu-id="de5e5-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="de5e5-107">Инструкция ссылается на имя файла или номер, который не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="de5e5-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="de5e5-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="de5e5-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="de5e5-109">Убедитесь, что имя файла задано в `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="de5e5-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="de5e5-110">Обратите внимание, что при вызове `FileClose` оператор без аргументов, могут случайно закрыты все открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="de5e5-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="de5e5-111">Если код создает номера файлов алгоритмически, убедитесь, что эти номера являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="de5e5-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="de5e5-112">Проверьте имена файлов, чтобы убедиться в том, что они соответствуют соглашениям операционной системы.</span><span class="sxs-lookup"><span data-stu-id="de5e5-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5e5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="de5e5-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="de5e5-114">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de5e5-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
