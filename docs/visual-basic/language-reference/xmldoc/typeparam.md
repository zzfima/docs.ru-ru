---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524619"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="f4fee-102">> \<typeparam (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4fee-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="f4fee-103">Определяет имя и описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f4fee-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4fee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4fee-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4fee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4fee-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f4fee-106">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f4fee-106">The name of the type parameter.</span></span> <span data-ttu-id="f4fee-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="f4fee-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f4fee-108">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f4fee-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4fee-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="f4fee-109">Remarks</span></span>  
 <span data-ttu-id="f4fee-110">Используйте тег `<typeparam>` в комментарии для объявления универсального типа или универсального члена, чтобы описать один из параметров типа.</span><span class="sxs-lookup"><span data-stu-id="f4fee-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f4fee-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="f4fee-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4fee-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f4fee-112">Example</span></span>  
 <span data-ttu-id="f4fee-113">В этом примере используется тег `<typeparam>` для описания параметра `id`.</span><span class="sxs-lookup"><span data-stu-id="f4fee-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f4fee-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f4fee-114">See also</span></span>

- [<span data-ttu-id="f4fee-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="f4fee-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
