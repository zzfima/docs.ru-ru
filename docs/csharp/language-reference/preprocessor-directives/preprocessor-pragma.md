---
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712459"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="2fe57-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2fe57-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="2fe57-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="2fe57-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="2fe57-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="2fe57-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="2fe57-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="2fe57-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="2fe57-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="2fe57-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="2fe57-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2fe57-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="2fe57-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2fe57-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="2fe57-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fe57-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fe57-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fe57-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="2fe57-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="2fe57-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="2fe57-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="2fe57-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe57-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2fe57-113">See also</span></span>

- [<span data-ttu-id="2fe57-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2fe57-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2fe57-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2fe57-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2fe57-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="2fe57-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="2fe57-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2fe57-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="2fe57-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2fe57-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
