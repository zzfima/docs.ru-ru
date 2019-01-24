---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 73ffb1319e6724a13a80b3cd1ca6985e4cbac05c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567065"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="905e4-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="905e4-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="905e4-103">Определяет имя параметра типа и описание.</span><span class="sxs-lookup"><span data-stu-id="905e4-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="905e4-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="905e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="905e4-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="905e4-106">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="905e4-106">The name of the type parameter.</span></span> <span data-ttu-id="905e4-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="905e4-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="905e4-108">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="905e4-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="905e4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="905e4-109">Remarks</span></span>  
 <span data-ttu-id="905e4-110">Используйте `<typeparam>` тег в комментарии для универсального типа или объявление универсального члена для описания одного из параметров типа.</span><span class="sxs-lookup"><span data-stu-id="905e4-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="905e4-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="905e4-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="905e4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="905e4-112">Example</span></span>  
 <span data-ttu-id="905e4-113">В этом примере используется `<typeparam>` тегов для описания `id` параметра.</span><span class="sxs-lookup"><span data-stu-id="905e4-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="905e4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="905e4-114">See also</span></span>
- [<span data-ttu-id="905e4-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="905e4-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
