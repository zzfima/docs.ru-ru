---
title: Исключение комментария XML должно содержать &#39;cref&#39; атрибут
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930032"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="d869f-102">Исключение комментария XML должно содержать &#39;cref&#39; атрибут</span><span class="sxs-lookup"><span data-stu-id="d869f-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="d869f-103">\<Исключение > тег предоставляет способ для документирования исключений, которые могут быть созданы с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="d869f-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="d869f-104">Необходимая `cref` атрибут назначает имя элемента, которое проверяется генератором документации.</span><span class="sxs-lookup"><span data-stu-id="d869f-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="d869f-105">Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.</span><span class="sxs-lookup"><span data-stu-id="d869f-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="d869f-106">**Идентификатор ошибки:** BC42319</span><span class="sxs-lookup"><span data-stu-id="d869f-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d869f-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d869f-107">To correct this error</span></span>  
  
-   <span data-ttu-id="d869f-108">Добавление `cref` атрибут исключение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d869f-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d869f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d869f-109">See Also</span></span>  
 [<span data-ttu-id="d869f-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="d869f-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="d869f-111">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="d869f-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="d869f-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d869f-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
