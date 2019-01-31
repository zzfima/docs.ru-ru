---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: ca0b298c0c95e018febbcfac95de7db05bffedb8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287889"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="155b4-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155b4-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="155b4-103">Указывает ссылку, которая отображается в разделе см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="155b4-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="155b4-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="155b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="155b4-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="155b4-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="155b4-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="155b4-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="155b4-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="155b4-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="155b4-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155b4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="155b4-109">Remarks</span></span>  
 <span data-ttu-id="155b4-110">Используйте `<seealso>` тег, чтобы указать текст, который будет отображаться в разделе см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="155b4-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="155b4-111">Тег [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="155b4-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="155b4-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="155b4-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="155b4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="155b4-113">Example</span></span>  
 <span data-ttu-id="155b4-114">В этом примере используется `<seealso>` тегом `DoesRecordExist` раздел для ссылки на примечаний `UpdateRecord` метод.</span><span class="sxs-lookup"><span data-stu-id="155b4-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="155b4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="155b4-115">See also</span></span>
- [<span data-ttu-id="155b4-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="155b4-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
