---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 9faf1ec7211493b8c0058439e9a6e3bcb293ea99
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289527"
---
# <a name="see-visual-basic"></a><span data-ttu-id="96286-102">\<см. в разделе > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96286-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="96286-103">Указывает ссылку на другой член.</span><span class="sxs-lookup"><span data-stu-id="96286-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96286-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96286-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96286-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96286-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="96286-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="96286-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="96286-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="96286-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="96286-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="96286-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96286-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="96286-109">Remarks</span></span>  
 <span data-ttu-id="96286-110">Используйте `<see>` тег, чтобы указать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="96286-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="96286-111">Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».</span><span class="sxs-lookup"><span data-stu-id="96286-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="96286-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="96286-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96286-113">Пример</span><span class="sxs-lookup"><span data-stu-id="96286-113">Example</span></span>  
 <span data-ttu-id="96286-114">В этом примере используется `<see>` тегом `UpdateRecord` раздел для ссылки на примечаний `DoesRecordExist` метод.</span><span class="sxs-lookup"><span data-stu-id="96286-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="96286-115">См. также</span><span class="sxs-lookup"><span data-stu-id="96286-115">See also</span></span>
- [<span data-ttu-id="96286-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="96286-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
