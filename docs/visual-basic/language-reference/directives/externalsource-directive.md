---
title: '#ExternalSource-директива (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556322"
---
# <a name="externalsource-directive"></a><span data-ttu-id="d2899-102">Директива #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="d2899-102">#ExternalSource Directive</span></span>
<span data-ttu-id="d2899-103">Указывает сопоставление между определенными строками исходного кода и текста, внешним по отношению к источнику.</span><span class="sxs-lookup"><span data-stu-id="d2899-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2899-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2899-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="d2899-105">Части</span><span class="sxs-lookup"><span data-stu-id="d2899-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="d2899-106">Путь к внешнему источнику.</span><span class="sxs-lookup"><span data-stu-id="d2899-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="d2899-107">Номер строки в первой строке из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d2899-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="d2899-108">Строка, где произошла ошибка из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d2899-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="d2899-109">Завершает блок `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="d2899-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2899-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2899-110">Remarks</span></span>  
 <span data-ttu-id="d2899-111">Эта директива используется только компилятор и отладчик.</span><span class="sxs-lookup"><span data-stu-id="d2899-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="d2899-112">Исходный файл может содержать директивы внешнего источника, которые задают сопоставление определенных строк кода в исходном файле и внешнего источника, например ASPX-файла текста.</span><span class="sxs-lookup"><span data-stu-id="d2899-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="d2899-113">Если ошибки, возникающие в указанном исходном коде во время компиляции, они определяются как поступающие от внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d2899-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="d2899-114">Директивы внешнего источника не влияют на компиляцию и не могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="d2899-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="d2899-115">Они предназначены для внутреннего использования только приложением.</span><span class="sxs-lookup"><span data-stu-id="d2899-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2899-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d2899-116">See Also</span></span>  
 [<span data-ttu-id="d2899-117">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="d2899-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
