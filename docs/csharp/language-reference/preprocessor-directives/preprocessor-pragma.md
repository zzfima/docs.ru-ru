---
title: '#pragma (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: a4829d5062474922d45a2f4f8e1cddf9023b6ad8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278813"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="b31c2-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b31c2-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="b31c2-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="b31c2-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="b31c2-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="b31c2-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="b31c2-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="b31c2-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="b31c2-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="b31c2-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="b31c2-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b31c2-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="b31c2-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b31c2-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="b31c2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b31c2-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b31c2-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="b31c2-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="b31c2-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b31c2-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="b31c2-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b31c2-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31c2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b31c2-113">See Also</span></span>  
 [<span data-ttu-id="b31c2-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b31c2-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b31c2-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b31c2-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b31c2-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="b31c2-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="b31c2-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b31c2-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [<span data-ttu-id="b31c2-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b31c2-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
