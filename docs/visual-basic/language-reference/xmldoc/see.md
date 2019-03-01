---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c0f1293fa0161a9a11b4e80301f5c4c4ddffe7b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969301"
---
# <a name="see-visual-basic"></a><span data-ttu-id="898e4-102">\<см. в разделе > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="898e4-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="898e4-103">Указывает ссылку на другой член.</span><span class="sxs-lookup"><span data-stu-id="898e4-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="898e4-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="898e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="898e4-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="898e4-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="898e4-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="898e4-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="898e4-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="898e4-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="898e4-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="898e4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="898e4-109">Remarks</span></span>  
 <span data-ttu-id="898e4-110">Используйте `<see>` тег, чтобы указать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="898e4-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="898e4-111">Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».</span><span class="sxs-lookup"><span data-stu-id="898e4-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="898e4-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="898e4-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="898e4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="898e4-113">Example</span></span>  
 <span data-ttu-id="898e4-114">В этом примере используется `<see>` тегом `UpdateRecord` раздел для ссылки на примечаний `DoesRecordExist` метод.</span><span class="sxs-lookup"><span data-stu-id="898e4-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="898e4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="898e4-115">See also</span></span>
- [<span data-ttu-id="898e4-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="898e4-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
