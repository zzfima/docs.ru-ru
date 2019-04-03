---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3e2bf7990343a325bbecc56f6d3754a77f1e08e2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818675"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="5273b-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5273b-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="5273b-103">Форматирует слово в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="5273b-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5273b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5273b-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5273b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5273b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5273b-106">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="5273b-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="5273b-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="5273b-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5273b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5273b-108">Remarks</span></span>  
 <span data-ttu-id="5273b-109">`<paramref>` Тег дает возможность указать, что слово является параметром.</span><span class="sxs-lookup"><span data-stu-id="5273b-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="5273b-110">Чтобы этот параметр особым образом могут обрабатываться XML-файле.</span><span class="sxs-lookup"><span data-stu-id="5273b-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="5273b-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="5273b-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5273b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5273b-112">Example</span></span>  
 <span data-ttu-id="5273b-113">В этом примере используется `<paramref>` тег для ссылки на `id` параметра.</span><span class="sxs-lookup"><span data-stu-id="5273b-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5273b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5273b-114">See also</span></span>

- [<span data-ttu-id="5273b-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="5273b-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
