---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 1d45c0c5fa95de9cfa345c0bdbf496aa227b9af5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604683"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="edd8c-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd8c-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="edd8c-103">Указывает ссылку, которая отображается в разделе см.</span><span class="sxs-lookup"><span data-stu-id="edd8c-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edd8c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edd8c-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edd8c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edd8c-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="edd8c-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="edd8c-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="edd8c-107">Компилятор проверяет, что данный элемент кода существует и передает `member` имени элемента в выходных данных XML.</span><span class="sxs-lookup"><span data-stu-id="edd8c-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="edd8c-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="edd8c-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edd8c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="edd8c-109">Remarks</span></span>  
 <span data-ttu-id="edd8c-110">Используйте `<seealso>` тег, чтобы указать текст, который будет отображаться в разделе см.</span><span class="sxs-lookup"><span data-stu-id="edd8c-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="edd8c-111">Тег [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="edd8c-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="edd8c-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="edd8c-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edd8c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="edd8c-113">Example</span></span>  
 <span data-ttu-id="edd8c-114">В этом примере используется `<seealso>` тегом `DoesRecordExist` раздел для обращения к примечаний `UpdateRecord` метод.</span><span class="sxs-lookup"><span data-stu-id="edd8c-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="edd8c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="edd8c-115">See Also</span></span>  
 [<span data-ttu-id="edd8c-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="edd8c-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
