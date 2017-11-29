---
title: "&lt;в разделе&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 010a3403d7748653648b323ad07f52bf93db2879
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="d47f1-102">&lt;в разделе&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d47f1-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="d47f1-103">Указывает ссылку на другой член.</span><span class="sxs-lookup"><span data-stu-id="d47f1-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d47f1-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d47f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d47f1-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d47f1-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="d47f1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d47f1-107">Компилятор проверяет, что данный элемент кода существует и передает `member` имени элемента в выходных данных XML.</span><span class="sxs-lookup"><span data-stu-id="d47f1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="d47f1-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="d47f1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d47f1-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d47f1-109">Remarks</span></span>  
 <span data-ttu-id="d47f1-110">Используйте `<see>` тег, чтобы указать ссылку в тексте.</span><span class="sxs-lookup"><span data-stu-id="d47f1-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="d47f1-111">Используйте [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) для указания текста, который может отображаться в разделе «См. также».</span><span class="sxs-lookup"><span data-stu-id="d47f1-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="d47f1-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d47f1-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d47f1-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d47f1-113">Example</span></span>  
 <span data-ttu-id="d47f1-114">В этом примере используется `<see>` тегом `UpdateRecord` раздел для обращения к примечаний `DoesRecordExist` метод.</span><span class="sxs-lookup"><span data-stu-id="d47f1-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d47f1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d47f1-115">See Also</span></span>  
 [<span data-ttu-id="d47f1-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d47f1-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
