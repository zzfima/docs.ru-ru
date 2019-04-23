---
title: Недопустимая длина записи
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979748"
---
# <a name="bad-record-length"></a><span data-ttu-id="1476a-102">Недопустимая длина записи</span><span class="sxs-lookup"><span data-stu-id="1476a-102">Bad record length</span></span>
<span data-ttu-id="1476a-103">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="1476a-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="1476a-104">Длина переменной записи, указанной в `FileGet`, `FileGetObject`, `FilePut` или `FilePutObject` инструкция отличается от длины, указанной в соответствующем `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="1476a-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="1476a-105">Эту переменную в `FilePut` или `FilePutObject` инструкция или включает строку переменной длины.</span><span class="sxs-lookup"><span data-stu-id="1476a-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="1476a-106">Эту переменную в `FilePut` или `FilePutObject` является или включает `Variant` типа.</span><span class="sxs-lookup"><span data-stu-id="1476a-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1476a-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1476a-107">To correct this error</span></span>  
  
1. <span data-ttu-id="1476a-108">Убедитесь, что сумма размеров переменных фиксированной длины в определяемый пользователем тип, определяющий тип переменной записи совпадает со значением, заданным в `FileOpen` инструкции `Len` предложение.</span><span class="sxs-lookup"><span data-stu-id="1476a-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="1476a-109">Если переменная в `FilePut` или `FilePutObject` инструкцию или включает строку переменной длины, то убедитесь, что строка переменной длины по крайней мере 2 символов, короче, чем длина записи, указанная в `Len` предложении `FileOpen` инструкция.</span><span class="sxs-lookup"><span data-stu-id="1476a-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="1476a-110">Если переменная в `FilePut` или `FilePutObject` является или включает `Variant` убедитесь, что строка переменной длины по крайней мере 4 байта короче, чем длина записи, указанной в `Len` предложении `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="1476a-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1476a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1476a-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
