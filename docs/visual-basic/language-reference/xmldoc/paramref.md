---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 78227a17584271f91283198e95f5aa389b3ef14b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352282"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="05a2f-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05a2f-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="05a2f-102">Formats a word as a parameter.</span><span class="sxs-lookup"><span data-stu-id="05a2f-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05a2f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05a2f-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="05a2f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="05a2f-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="05a2f-105">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="05a2f-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="05a2f-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="05a2f-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05a2f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="05a2f-107">Remarks</span></span>  
 <span data-ttu-id="05a2f-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span><span class="sxs-lookup"><span data-stu-id="05a2f-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="05a2f-109">The XML file can be processed to format this parameter in some distinct way.</span><span class="sxs-lookup"><span data-stu-id="05a2f-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="05a2f-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="05a2f-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a2f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="05a2f-111">Example</span></span>  
 <span data-ttu-id="05a2f-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span><span class="sxs-lookup"><span data-stu-id="05a2f-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="05a2f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="05a2f-113">See also</span></span>

- [<span data-ttu-id="05a2f-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="05a2f-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
