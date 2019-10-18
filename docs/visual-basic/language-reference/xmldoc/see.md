---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524655"
---
# <a name="see-visual-basic"></a><span data-ttu-id="83367-102">> \<see (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83367-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="83367-103">Указывает ссылку на другой элемент.</span><span class="sxs-lookup"><span data-stu-id="83367-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83367-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83367-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="83367-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83367-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="83367-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="83367-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="83367-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="83367-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="83367-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="83367-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83367-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="83367-109">Remarks</span></span>  
 <span data-ttu-id="83367-110">Используйте тег `<see>`, чтобы указать ссылку в тексте.</span><span class="sxs-lookup"><span data-stu-id="83367-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="83367-111">Используйте [\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) , чтобы указать текст, который может появиться в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="83367-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="83367-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="83367-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83367-113">Пример</span><span class="sxs-lookup"><span data-stu-id="83367-113">Example</span></span>  
 <span data-ttu-id="83367-114">В этом примере используется тег `<see>` в разделе `UpdateRecord` примечаний для ссылки на метод `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="83367-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="83367-115">См. также</span><span class="sxs-lookup"><span data-stu-id="83367-115">See also</span></span>

- [<span data-ttu-id="83367-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="83367-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
