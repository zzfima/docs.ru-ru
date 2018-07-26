---
title: Практическое руководство. Создание XML-документации в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243883"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="eba6e-102">Практическое руководство. Создание XML-документации в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eba6e-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="eba6e-103">В этом примере показано, как добавить в код комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="eba6e-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="eba6e-104">Для создания XML-документации для типа или члена</span><span class="sxs-lookup"><span data-stu-id="eba6e-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="eba6e-105">В **редактор кода**, поместите курсор на одну строку выше типа или члена, для которого требуется создать документацию.</span><span class="sxs-lookup"><span data-stu-id="eba6e-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="eba6e-106">Тип `'''` (три знака одинарных кавычек).</span><span class="sxs-lookup"><span data-stu-id="eba6e-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="eba6e-107">Схема XML для типа или члена добавляется в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="eba6e-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="eba6e-108">Добавление описательной информации между соответствующими тегами.</span><span class="sxs-lookup"><span data-stu-id="eba6e-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eba6e-109">Если вы добавите дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.</span><span class="sxs-lookup"><span data-stu-id="eba6e-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="eba6e-110">Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="eba6e-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="eba6e-111">IntelliSense отображает текст из \<summary > тег для типа или члена.</span><span class="sxs-lookup"><span data-stu-id="eba6e-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="eba6e-112">Скомпилируйте код, чтобы создать XML-файл, содержащий комментарии к документации.</span><span class="sxs-lookup"><span data-stu-id="eba6e-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="eba6e-113">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="eba6e-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba6e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="eba6e-114">See Also</span></span>  
 [<span data-ttu-id="eba6e-115">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="eba6e-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="eba6e-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="eba6e-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="eba6e-117">/doc</span><span class="sxs-lookup"><span data-stu-id="eba6e-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
