---
title: '&lt;Пример&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 2de91d828fd9706b66f4c810486e54e2d3062de0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524521"
---
# <a name="ltexamplegt-visual-basic"></a><span data-ttu-id="04513-102">&lt;Пример&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04513-102">&lt;example&gt; (Visual Basic)</span></span>
<span data-ttu-id="04513-103">Задает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="04513-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04513-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04513-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04513-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04513-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="04513-106">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="04513-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04513-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="04513-107">Remarks</span></span>  
 <span data-ttu-id="04513-108">`<example>` Тег позволяет указать пример демонстрирует использование метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="04513-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="04513-109">Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="04513-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="04513-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="04513-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04513-111">Пример</span><span class="sxs-lookup"><span data-stu-id="04513-111">Example</span></span>  
 <span data-ttu-id="04513-112">В этом примере используется `<example>` тега для включения примера использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="04513-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04513-113">См. также</span><span class="sxs-lookup"><span data-stu-id="04513-113">See Also</span></span>  
 [<span data-ttu-id="04513-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="04513-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
