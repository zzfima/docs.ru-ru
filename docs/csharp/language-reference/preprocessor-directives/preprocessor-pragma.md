---
title: "#<a name=\"pragma-c-reference\"></a>pragma (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e03fc387b105c1dee3b7fed93263ad8ef22d5934
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-c-reference"></a><span data-ttu-id="5e459-102">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5e459-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="5e459-103">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="5e459-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="5e459-104">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="5e459-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="5e459-105">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="5e459-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="5e459-106">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="5e459-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="5e459-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="5e459-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="5e459-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="5e459-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="5e459-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e459-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e459-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e459-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="5e459-111">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="5e459-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="5e459-112">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="5e459-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e459-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5e459-113">See Also</span></span>  
 <span data-ttu-id="5e459-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e459-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5e459-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e459-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5e459-116">[Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e459-116">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="5e459-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span><span class="sxs-lookup"><span data-stu-id="5e459-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span></span>  
 [<span data-ttu-id="5e459-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="5e459-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

