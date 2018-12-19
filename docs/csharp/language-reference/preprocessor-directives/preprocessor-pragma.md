---
title: '#pragma. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65867bc441711193f93142d1c65122b6bc60c25d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241831"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="2dd1d-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2dd1d-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="2dd1d-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="2dd1d-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="2dd1d-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="2dd1d-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="2dd1d-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="2dd1d-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="2dd1d-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="2dd1d-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="2dd1d-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2dd1d-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="2dd1d-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2dd1d-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="2dd1d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dd1d-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dd1d-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dd1d-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="2dd1d-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="2dd1d-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="2dd1d-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="2dd1d-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd1d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2dd1d-113">See Also</span></span>

- [<span data-ttu-id="2dd1d-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2dd1d-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2dd1d-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2dd1d-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2dd1d-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="2dd1d-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="2dd1d-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2dd1d-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="2dd1d-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2dd1d-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
