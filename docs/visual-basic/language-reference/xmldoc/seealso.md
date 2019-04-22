---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0df999ef502bf61bdfb65cb472947b93efded36e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823484"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="43628-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43628-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="43628-103">Указывает ссылку, которая отображается в разделе см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="43628-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43628-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43628-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="43628-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43628-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="43628-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="43628-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="43628-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="43628-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="43628-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="43628-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43628-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="43628-109">Remarks</span></span>  
 <span data-ttu-id="43628-110">Используйте `<seealso>` тег, чтобы указать текст, который будет отображаться в разделе см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="43628-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="43628-111">Тег [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="43628-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="43628-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="43628-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43628-113">Пример</span><span class="sxs-lookup"><span data-stu-id="43628-113">Example</span></span>  
 <span data-ttu-id="43628-114">В этом примере используется `<seealso>` тегом `DoesRecordExist` раздел для ссылки на примечаний `UpdateRecord` метод.</span><span class="sxs-lookup"><span data-stu-id="43628-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="43628-115">См. также</span><span class="sxs-lookup"><span data-stu-id="43628-115">See also</span></span>

- [<span data-ttu-id="43628-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="43628-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
