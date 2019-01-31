---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 75e6f966f8baac2fd3c863c7caea939d80bfc41b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255528"
---
# <a name="example-visual-basic"></a><span data-ttu-id="eadbe-102">\<Пример > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eadbe-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="eadbe-103">Задает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="eadbe-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eadbe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eadbe-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eadbe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eadbe-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="eadbe-106">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="eadbe-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eadbe-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="eadbe-107">Remarks</span></span>  
 <span data-ttu-id="eadbe-108">`<example>` Тег позволяет указать пример демонстрирует использование метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="eadbe-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="eadbe-109">Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="eadbe-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="eadbe-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="eadbe-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eadbe-111">Пример</span><span class="sxs-lookup"><span data-stu-id="eadbe-111">Example</span></span>  
 <span data-ttu-id="eadbe-112">В этом примере используется `<example>` тега для включения примера использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="eadbe-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eadbe-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eadbe-113">See also</span></span>
- [<span data-ttu-id="eadbe-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="eadbe-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
