---
title: "#<a name=\"externalsource-directive\"></a>ExternalSource-директива"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a><span data-ttu-id="cc5be-102">Директива #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="cc5be-102">#ExternalSource Directive</span></span>
<span data-ttu-id="cc5be-103">Указывает сопоставление между определенными строками исходного кода и текста, внешних по отношению к источнику.</span><span class="sxs-lookup"><span data-stu-id="cc5be-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc5be-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="cc5be-105">Части</span><span class="sxs-lookup"><span data-stu-id="cc5be-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="cc5be-106">Путь к внешнему источнику.</span><span class="sxs-lookup"><span data-stu-id="cc5be-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="cc5be-107">Номер строки в первой строке внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="cc5be-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="cc5be-108">Строка, где произошла ошибка из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="cc5be-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="cc5be-109">Завершает блок `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="cc5be-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc5be-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc5be-110">Remarks</span></span>  
 <span data-ttu-id="cc5be-111">Эта директива используется только компилятором и отладчиком.</span><span class="sxs-lookup"><span data-stu-id="cc5be-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="cc5be-112">Исходный файл может содержать директивы внешнего источника, которые задают сопоставление между определенные строки кода в файле исходного кода и текстом, внешним по отношению к источнику, например ASPX-файл.</span><span class="sxs-lookup"><span data-stu-id="cc5be-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="cc5be-113">Если ошибки, возникающие в указанном коде источника во время компиляции, они определяются как поступающие из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="cc5be-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="cc5be-114">Директивы внешнего источника не влияют на компиляцию и не могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="cc5be-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="cc5be-115">Они предназначены для внутреннего использования только приложением.</span><span class="sxs-lookup"><span data-stu-id="cc5be-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5be-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cc5be-116">See Also</span></span>  
 [<span data-ttu-id="cc5be-117">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="cc5be-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
