---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 3f40177b717452f316672c29c6455faf33e01b4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282715"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="aabdd-102">\<Сводка > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aabdd-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="aabdd-103">Задает сводку элемента.</span><span class="sxs-lookup"><span data-stu-id="aabdd-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aabdd-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aabdd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aabdd-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="aabdd-106">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="aabdd-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aabdd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aabdd-107">Remarks</span></span>  
 <span data-ttu-id="aabdd-108">Используйте `<summary>` тегов для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="aabdd-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="aabdd-109">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md).</span><span class="sxs-lookup"><span data-stu-id="aabdd-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="aabdd-110">Текст для `<summary>` тег является единственным источником сведений о типе для технологии IntelliSense, а также отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="aabdd-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="aabdd-111">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="aabdd-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="aabdd-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="aabdd-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aabdd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="aabdd-113">Example</span></span>  
 <span data-ttu-id="aabdd-114">В этом примере используется `<summary>` тегов для описания `ResetCounter` метод и `Counter` свойство.</span><span class="sxs-lookup"><span data-stu-id="aabdd-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="aabdd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aabdd-115">See also</span></span>
- [<span data-ttu-id="aabdd-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="aabdd-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
