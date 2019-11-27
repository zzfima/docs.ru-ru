---
title: '#Директива ExternalSource'
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
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343835"
---
# <a name="externalsource-directive"></a><span data-ttu-id="b67aa-102">Директива #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="b67aa-102">#ExternalSource Directive</span></span>

<span data-ttu-id="b67aa-103">Указывает сопоставление между конкретными строками исходного кода и текстом, внешним по отношению к источнику.</span><span class="sxs-lookup"><span data-stu-id="b67aa-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b67aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b67aa-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="b67aa-105">Части</span><span class="sxs-lookup"><span data-stu-id="b67aa-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="b67aa-106">Путь к внешнему источнику.</span><span class="sxs-lookup"><span data-stu-id="b67aa-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="b67aa-107">Номер строки первой строки внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="b67aa-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="b67aa-108">Строка, в которой возникла ошибка во внешнем источнике.</span><span class="sxs-lookup"><span data-stu-id="b67aa-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="b67aa-109">Завершает блок `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="b67aa-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b67aa-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b67aa-110">Remarks</span></span>  

 <span data-ttu-id="b67aa-111">Эта директива используется только компилятором и отладчиком.</span><span class="sxs-lookup"><span data-stu-id="b67aa-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="b67aa-112">Исходный файл может содержать директивы External Source, которые указывают на сопоставление между конкретными строками кода в исходном файле и внешним по отношению к источнику текстом, например ASPX-файлу.</span><span class="sxs-lookup"><span data-stu-id="b67aa-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="b67aa-113">Если во время компиляции обнаружены ошибки в указанном исходном коде, они определяются как поступающие из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="b67aa-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="b67aa-114">Директивы External Source не влияют на компиляцию и не могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="b67aa-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="b67aa-115">Они предназначены только для внутреннего использования приложением.</span><span class="sxs-lookup"><span data-stu-id="b67aa-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67aa-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b67aa-116">See also</span></span>

- [<span data-ttu-id="b67aa-117">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="b67aa-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
