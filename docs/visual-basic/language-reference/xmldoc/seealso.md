---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0231ff748949874f4b477cac15d891d313b25f4f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524645"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="b154b-102">> \<seealso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b154b-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="b154b-103">Указывает ссылку, которая отображается в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="b154b-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b154b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b154b-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b154b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b154b-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="b154b-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="b154b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b154b-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b154b-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="b154b-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="b154b-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b154b-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b154b-109">Remarks</span></span>  
 <span data-ttu-id="b154b-110">Используйте тег `<seealso>`, чтобы указать текст, который должен отображаться в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="b154b-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="b154b-111">Тег [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="b154b-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="b154b-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="b154b-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b154b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b154b-113">Example</span></span>  
 <span data-ttu-id="b154b-114">В этом примере используется тег `<seealso>` в разделе `DoesRecordExist` примечаний для ссылки на метод `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="b154b-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b154b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b154b-115">See also</span></span>

- [<span data-ttu-id="b154b-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="b154b-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
