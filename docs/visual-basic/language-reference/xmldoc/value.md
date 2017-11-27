---
title: "&lt;значение&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="8c3bc-102">&lt;значение&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c3bc-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="8c3bc-103">Задает описание свойства.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c3bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c3bc-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c3bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c3bc-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8c3bc-106">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c3bc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c3bc-107">Remarks</span></span>  
 <span data-ttu-id="8c3bc-108">Используйте `<value>` тегов для описания свойства.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8c3bc-109">Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio добавит [ \<сводки >](../../../visual-basic/language-reference/xmldoc/summary.md) тег для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8c3bc-110">Следует затем вручную добавить `<value>` тегов для описания значение, представляющее свойство.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8c3bc-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="8c3bc-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c3bc-112">Пример</span><span class="sxs-lookup"><span data-stu-id="8c3bc-112">Example</span></span>  
 <span data-ttu-id="8c3bc-113">В этом примере используется `<value>` тегов для описания какое значение `Counter` содержится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="8c3bc-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8c3bc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8c3bc-114">See Also</span></span>  
 [<span data-ttu-id="8c3bc-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="8c3bc-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
