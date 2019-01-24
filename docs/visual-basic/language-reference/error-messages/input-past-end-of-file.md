---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 29a9b5ce3c3f8e6a02b52beda1338fd699143570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491341"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="c6e36-102">Оператор Input обнаружил конец файла</span><span class="sxs-lookup"><span data-stu-id="c6e36-102">Input past end of file</span></span>
<span data-ttu-id="c6e36-103">Либо `Input` считывает данные из файла, который является пустым или в которой все данные используются, или была использована инструкция `EOF` функцию с файл открыт для двоичного доступа.</span><span class="sxs-lookup"><span data-stu-id="c6e36-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6e36-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c6e36-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="c6e36-105">Используйте `EOF` функции непосредственно перед `Input` инструкцию, чтобы определить конец файла.</span><span class="sxs-lookup"><span data-stu-id="c6e36-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="c6e36-106">Если файл открыт для двоичного доступа, используйте `Seek` и `Loc`.</span><span class="sxs-lookup"><span data-stu-id="c6e36-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e36-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e36-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
