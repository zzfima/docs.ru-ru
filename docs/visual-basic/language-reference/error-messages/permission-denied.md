---
title: Доступ запрещен (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318836"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="c5720-102">Доступ запрещен (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5720-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="c5720-103">Предпринята попытка записи на диск защищен от записи или доступа к заблокированного файла.</span><span class="sxs-lookup"><span data-stu-id="c5720-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5720-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c5720-104">To correct this error</span></span>  
  
1. <span data-ttu-id="c5720-105">Чтобы открыть файл защищен от записи, измените атрибут защиту от записи файла.</span><span class="sxs-lookup"><span data-stu-id="c5720-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="c5720-106">Убедитесь, что файл не заблокирован другим процессом и ожидания для открытия файла, до ее снятия другим процессом.</span><span class="sxs-lookup"><span data-stu-id="c5720-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="c5720-107">Для доступа к реестру, убедитесь, что разрешения пользователя включают этот тип доступа к реестру.</span><span class="sxs-lookup"><span data-stu-id="c5720-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5720-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c5720-108">See also</span></span>

- [<span data-ttu-id="c5720-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="c5720-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
