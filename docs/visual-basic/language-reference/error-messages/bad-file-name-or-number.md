---
title: Недопустимое имя файла или номер
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: c57f431350d4f63507ee7374616b62ca32151c86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639410"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="e6551-102">Недопустимое имя файла или номер</span><span class="sxs-lookup"><span data-stu-id="e6551-102">Bad file name or number</span></span>
<span data-ttu-id="e6551-103">Произошла ошибка при попытке доступа к указанному файлу.</span><span class="sxs-lookup"><span data-stu-id="e6551-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="e6551-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="e6551-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="e6551-105">Оператор ссылается на файл с именем файла или номер, который не был указан в `FileOpen` инструкции или был указан в `FileOpen` инструкции однако впоследствии был закрыт.</span><span class="sxs-lookup"><span data-stu-id="e6551-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="e6551-106">Инструкция ссылается на файл с номером, который находится за пределами диапазона номеров файлов.</span><span class="sxs-lookup"><span data-stu-id="e6551-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="e6551-107">Инструкция ссылается на имя файла или число, которое является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="e6551-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e6551-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e6551-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e6551-109">Убедитесь, что имя файла указано в `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e6551-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="e6551-110">Обратите внимание, что при вызове `FileClose` инструкции без аргументов, могут случайно закрыты все открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="e6551-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="e6551-111">Если ваш код создает номера файлов алгоритмически, убедитесь, что значения действительны.</span><span class="sxs-lookup"><span data-stu-id="e6551-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="e6551-112">Проверьте имена файлов, чтобы убедиться в том, что она соответствует соглашениям операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e6551-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6551-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e6551-113">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="e6551-114">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6551-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
