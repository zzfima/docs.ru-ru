---
title: '#pragma (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 5ae397cc61e0c6b58ed2079369131ebb7e352eae
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482939"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="b2674-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b2674-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="b2674-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="b2674-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="b2674-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="b2674-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="b2674-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="b2674-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="b2674-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="b2674-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="b2674-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b2674-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="b2674-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b2674-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="b2674-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2674-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2674-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2674-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="b2674-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b2674-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="b2674-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="b2674-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2674-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b2674-113">See Also</span></span>

- [<span data-ttu-id="b2674-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b2674-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b2674-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b2674-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b2674-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="b2674-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="b2674-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b2674-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="b2674-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b2674-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
