---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 63b099144b9da601a7b52a738f5a3173097ae257
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813162"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="b3682-102">Оператор Input обнаружил конец файла</span><span class="sxs-lookup"><span data-stu-id="b3682-102">Input past end of file</span></span>
<span data-ttu-id="b3682-103">Либо `Input` считывает данные из файла, который является пустым или в которой все данные используются, или была использована инструкция `EOF` функцию с файл открыт для двоичного доступа.</span><span class="sxs-lookup"><span data-stu-id="b3682-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3682-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b3682-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="b3682-105">Используйте `EOF` функции непосредственно перед `Input` инструкцию, чтобы определить конец файла.</span><span class="sxs-lookup"><span data-stu-id="b3682-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="b3682-106">Если файл открыт для двоичного доступа, используйте `Seek` и `Loc`.</span><span class="sxs-lookup"><span data-stu-id="b3682-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3682-107">См. также</span><span class="sxs-lookup"><span data-stu-id="b3682-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
