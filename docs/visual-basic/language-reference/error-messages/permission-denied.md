---
title: В разрешении отказано
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: 410301a1e99040fc617ab1bf1e851329ab3072d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347007"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="68169-102">Доступ запрещен (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68169-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="68169-103">Предпринята попытка записи на диск, защищенный с помощью записи, или для доступа к заблокированному файлу.</span><span class="sxs-lookup"><span data-stu-id="68169-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="68169-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="68169-104">To correct this error</span></span>  
  
1. <span data-ttu-id="68169-105">Чтобы открыть защищенный от записи файл, измените атрибут защиты записи файла.</span><span class="sxs-lookup"><span data-stu-id="68169-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="68169-106">Убедитесь, что файл не заблокирован другим процессом, и дождитесь открытия файла, пока другой процесс не выпустит его.</span><span class="sxs-lookup"><span data-stu-id="68169-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="68169-107">Чтобы получить доступ к реестру, убедитесь, что разрешения пользователя включают этот тип доступа к реестру.</span><span class="sxs-lookup"><span data-stu-id="68169-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68169-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="68169-108">See also</span></span>

- [<span data-ttu-id="68169-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="68169-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
