---
title: '#pragma. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 8b39d6760a5e30986d5d4bbe9bb1281dbf6742a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471017"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="b3458-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b3458-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="b3458-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="b3458-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="b3458-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="b3458-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="b3458-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="b3458-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="b3458-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="b3458-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="b3458-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b3458-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="b3458-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b3458-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="b3458-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3458-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3458-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3458-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="b3458-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b3458-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="b3458-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b3458-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3458-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b3458-113">See also</span></span>

- [<span data-ttu-id="b3458-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b3458-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="b3458-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b3458-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b3458-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="b3458-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
- [<span data-ttu-id="b3458-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b3458-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="b3458-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b3458-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
