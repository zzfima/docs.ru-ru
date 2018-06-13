---
title: Исключение комментария XML должно содержать &#39;cref&#39; атрибута
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: ee91513ef94e2abbe01d3ac09796b7fdf8e129ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597387"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="bf4d5-102">Исключение комментария XML должно содержать &#39;cref&#39; атрибута</span><span class="sxs-lookup"><span data-stu-id="bf4d5-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="bf4d5-103">\<Исключение > тег предоставляет способ документирования исключений, которые могут быть созданы с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="bf4d5-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="bf4d5-104">Необходимая `cref` атрибут назначает имя элемента, которое проверяется генератором документации.</span><span class="sxs-lookup"><span data-stu-id="bf4d5-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="bf4d5-105">Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.</span><span class="sxs-lookup"><span data-stu-id="bf4d5-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="bf4d5-106">**Идентификатор ошибки:** BC42319</span><span class="sxs-lookup"><span data-stu-id="bf4d5-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf4d5-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bf4d5-107">To correct this error</span></span>  
  
-   <span data-ttu-id="bf4d5-108">Добавить `cref` атрибут исключение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bf4d5-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bf4d5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bf4d5-109">See Also</span></span>  
 [<span data-ttu-id="bf4d5-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="bf4d5-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="bf4d5-111">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="bf4d5-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="bf4d5-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="bf4d5-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
