---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: a1dea0bcc40de8dea986e93a25617f607383ec21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969223"
---
# <a name="example-visual-basic"></a><span data-ttu-id="465ce-102">\<Пример > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="465ce-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="465ce-103">Задает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="465ce-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="465ce-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="465ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="465ce-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="465ce-106">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="465ce-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="465ce-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="465ce-107">Remarks</span></span>  
 <span data-ttu-id="465ce-108">`<example>` Тег позволяет указать пример демонстрирует использование метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="465ce-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="465ce-109">Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="465ce-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="465ce-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="465ce-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="465ce-111">Пример</span><span class="sxs-lookup"><span data-stu-id="465ce-111">Example</span></span>  
 <span data-ttu-id="465ce-112">В этом примере используется `<example>` тега для включения примера использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="465ce-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="465ce-113">См. также</span><span class="sxs-lookup"><span data-stu-id="465ce-113">See also</span></span>
- [<span data-ttu-id="465ce-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="465ce-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
