---
title: Недопустимая длина записи
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 37d9da67656ec4821903d8ba67a27ef10f1a437d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728873"
---
# <a name="bad-record-length"></a><span data-ttu-id="208aa-102">Недопустимая длина записи</span><span class="sxs-lookup"><span data-stu-id="208aa-102">Bad record length</span></span>
<span data-ttu-id="208aa-103">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="208aa-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="208aa-104">Длина переменной записи, указанной в `FileGet`, `FileGetObject`, `FilePut` или `FilePutObject` инструкция отличается от длины, указанной в соответствующем `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="208aa-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="208aa-105">Эту переменную в `FilePut` или `FilePutObject` инструкция или включает строку переменной длины.</span><span class="sxs-lookup"><span data-stu-id="208aa-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="208aa-106">Эту переменную в `FilePut` или `FilePutObject` является или включает `Variant` типа.</span><span class="sxs-lookup"><span data-stu-id="208aa-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="208aa-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="208aa-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="208aa-108">Убедитесь, что сумма размеров переменных фиксированной длины в определяемый пользователем тип, определяющий тип переменной записи совпадает со значением, заданным в `FileOpen` инструкции `Len` предложение.</span><span class="sxs-lookup"><span data-stu-id="208aa-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2.  <span data-ttu-id="208aa-109">Если переменная в `FilePut` или `FilePutObject` инструкцию или включает строку переменной длины, то убедитесь, что строка переменной длины по крайней мере 2 символов, короче, чем длина записи, указанная в `Len` предложении `FileOpen` инструкция.</span><span class="sxs-lookup"><span data-stu-id="208aa-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3.  <span data-ttu-id="208aa-110">Если переменная в `FilePut` или `FilePutObject` является или включает `Variant` убедитесь, что строка переменной длины по крайней мере 4 байта короче, чем длина записи, указанной в `Len` предложении `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="208aa-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208aa-111">См. также</span><span class="sxs-lookup"><span data-stu-id="208aa-111">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
