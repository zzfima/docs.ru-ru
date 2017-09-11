---
title: "Практическое руководство: Создание XML-документации в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 3171877f4fa1913b5535d71d671cea97b5a22850
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="ac04e-102">Практическое руководство. Создание XML-документации в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac04e-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="ac04e-103">В этом примере показано, как добавить в код комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="ac04e-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="ac04e-104">Создание XML-документации для типа или члена</span><span class="sxs-lookup"><span data-stu-id="ac04e-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="ac04e-105">В **редактор кода**, поместите курсор на одну строку выше типа или члена, для которого требуется создать документацию.</span><span class="sxs-lookup"><span data-stu-id="ac04e-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="ac04e-106">Тип `'''` (три знака одинарных кавычек).</span><span class="sxs-lookup"><span data-stu-id="ac04e-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="ac04e-107">Схема XML для типа или члена добавляется в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="ac04e-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="ac04e-108">Добавление описательной информации между соответствующими тегами.</span><span class="sxs-lookup"><span data-stu-id="ac04e-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac04e-109">Если добавить дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.</span><span class="sxs-lookup"><span data-stu-id="ac04e-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="ac04e-110">Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="ac04e-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="ac04e-111">IntelliSense отображает текст из \<Сводка настроек тег для типа или члена.</span><span class="sxs-lookup"><span data-stu-id="ac04e-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="ac04e-112">Скомпилируйте код для создания XML-файл, содержащий комментарии к документации.</span><span class="sxs-lookup"><span data-stu-id="ac04e-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="ac04e-113">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="ac04e-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac04e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ac04e-114">See Also</span></span>  
 <span data-ttu-id="ac04e-115">[Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ac04e-115">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="ac04e-116"> [Теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="ac04e-116"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="ac04e-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span><span class="sxs-lookup"><span data-stu-id="ac04e-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span></span>
