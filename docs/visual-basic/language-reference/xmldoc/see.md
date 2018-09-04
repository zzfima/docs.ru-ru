---
title: '&lt;см. в разделе&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 78311651593d3d4a47c723f64a9a74d4660f7c90
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535081"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="6c5dd-102">&lt;см. в разделе&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c5dd-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="6c5dd-103">Указывает ссылку на другой член.</span><span class="sxs-lookup"><span data-stu-id="6c5dd-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c5dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c5dd-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c5dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c5dd-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="6c5dd-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="6c5dd-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="6c5dd-107">Компилятор проверяет, что данный элемент кода существует и передает `member` имени элемента в выходных данных XML.</span><span class="sxs-lookup"><span data-stu-id="6c5dd-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="6c5dd-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="6c5dd-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c5dd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c5dd-109">Remarks</span></span>  
 <span data-ttu-id="6c5dd-110">Используйте `<see>` тег, чтобы указать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="6c5dd-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="6c5dd-111">Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».</span><span class="sxs-lookup"><span data-stu-id="6c5dd-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="6c5dd-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="6c5dd-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c5dd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6c5dd-113">Example</span></span>  
 <span data-ttu-id="6c5dd-114">В этом примере используется `<see>` тегом `UpdateRecord` раздел для ссылки на примечаний `DoesRecordExist` метод.</span><span class="sxs-lookup"><span data-stu-id="6c5dd-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6c5dd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6c5dd-115">See Also</span></span>  
 [<span data-ttu-id="6c5dd-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="6c5dd-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
