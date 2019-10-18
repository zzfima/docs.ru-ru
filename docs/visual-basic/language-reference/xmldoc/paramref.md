---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 85171bd8deeb5f54c4560bb8b2339107bb8d8c68
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524707"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="e1e10-102">> \<paramref (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1e10-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="e1e10-103">Форматирует слово как параметр.</span><span class="sxs-lookup"><span data-stu-id="e1e10-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1e10-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1e10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1e10-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e1e10-106">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="e1e10-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="e1e10-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="e1e10-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1e10-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e1e10-108">Remarks</span></span>  
 <span data-ttu-id="e1e10-109">Тег `<paramref>` дает возможность указать, что слово является параметром.</span><span class="sxs-lookup"><span data-stu-id="e1e10-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="e1e10-110">XML-файл может быть обработан для того, чтобы отформатировать этот параметр определенным образом.</span><span class="sxs-lookup"><span data-stu-id="e1e10-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="e1e10-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="e1e10-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e10-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e10-112">Example</span></span>  
 <span data-ttu-id="e1e10-113">В этом примере используется тег `<paramref>` для ссылки на параметр `id`.</span><span class="sxs-lookup"><span data-stu-id="e1e10-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e1e10-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e10-114">See also</span></span>

- [<span data-ttu-id="e1e10-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="e1e10-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
