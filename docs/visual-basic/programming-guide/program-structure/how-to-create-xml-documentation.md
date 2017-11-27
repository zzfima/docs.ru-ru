---
title: "Практическое руководство. Создание XML-документации в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="95fca-102">Практическое руководство. Создание XML-документации в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95fca-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="95fca-103">В этом примере показано, как добавить в код комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="95fca-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="95fca-104">Для создания XML-документации для типа или члена</span><span class="sxs-lookup"><span data-stu-id="95fca-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="95fca-105">В **редактор кода**, поместите курсор на строку выше тип или член, для которого требуется создать документацию.</span><span class="sxs-lookup"><span data-stu-id="95fca-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="95fca-106">Тип `'''` (три знака одинарных кавычек).</span><span class="sxs-lookup"><span data-stu-id="95fca-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="95fca-107">Схема XML для типа или члена добавляется в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="95fca-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="95fca-108">Добавьте описательные сведения между соответствующими тегами.</span><span class="sxs-lookup"><span data-stu-id="95fca-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95fca-109">Если добавить дополнительные строки внутри блока XML-документации, каждая строка должна начинаться с `'''`.</span><span class="sxs-lookup"><span data-stu-id="95fca-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="95fca-110">Добавьте дополнительный код, который использует тип или член с новые комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="95fca-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="95fca-111">IntelliSense отображает текст из \<сводки > тег для типа или члена.</span><span class="sxs-lookup"><span data-stu-id="95fca-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="95fca-112">Скомпилируйте код для создания XML-файл, содержащий комментарии документации.</span><span class="sxs-lookup"><span data-stu-id="95fca-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="95fca-113">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="95fca-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fca-114">См. также</span><span class="sxs-lookup"><span data-stu-id="95fca-114">See Also</span></span>  
 [<span data-ttu-id="95fca-115">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="95fca-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="95fca-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="95fca-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="95fca-117">/doc</span><span class="sxs-lookup"><span data-stu-id="95fca-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
