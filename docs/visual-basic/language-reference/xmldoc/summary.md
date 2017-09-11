---
title: "&lt;Сводка&gt; (Visual Basic) | Документы Microsoft"
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 42321daf092c4b637d2f75fb7f6d7e95201791ba
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="ad71e-102">&lt;Сводка&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad71e-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="ad71e-103">Задает сводку элемента.</span><span class="sxs-lookup"><span data-stu-id="ad71e-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad71e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad71e-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad71e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad71e-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="ad71e-106">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="ad71e-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad71e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad71e-107">Remarks</span></span>  
 <span data-ttu-id="ad71e-108">Используйте `<summary>` тег для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="ad71e-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="ad71e-109">Используйте [ \<примечания настроек](../../../visual-basic/language-reference/xmldoc/remarks.md) Чтобы добавить дополнительную информацию для описания типа.</span><span class="sxs-lookup"><span data-stu-id="ad71e-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="ad71e-110">Текст для `<summary>` тег является единственным источником информации о типе в IntelliSense, а также отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="ad71e-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="ad71e-111">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="ad71e-111">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="ad71e-112">Скомпилируйте с [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) чтобы обработать комментарии документации в файл.</span><span class="sxs-lookup"><span data-stu-id="ad71e-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad71e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ad71e-113">Example</span></span>  
 <span data-ttu-id="ad71e-114">В этом примере используется `<summary>` тегов для описания `ResetCounter` метод и `Counter` свойства.</span><span class="sxs-lookup"><span data-stu-id="ad71e-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 <span data-ttu-id="ad71e-115">[!code-vb[VbVbcnXmlDocComments&#1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad71e-115">[!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad71e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ad71e-116">See Also</span></span>  
 [<span data-ttu-id="ad71e-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="ad71e-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
