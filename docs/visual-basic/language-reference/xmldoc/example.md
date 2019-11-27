---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f36ac1337dd0d1400180fbd3deae2bb24ad9c58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348485"
---
# <a name="example-visual-basic"></a><span data-ttu-id="18704-101">Пример > \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18704-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="18704-102">Указывает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="18704-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18704-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18704-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="18704-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="18704-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="18704-105">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="18704-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18704-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="18704-106">Remarks</span></span>  
 <span data-ttu-id="18704-107">Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="18704-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="18704-108">Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="18704-108">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="18704-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="18704-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18704-110">Пример</span><span class="sxs-lookup"><span data-stu-id="18704-110">Example</span></span>  
 <span data-ttu-id="18704-111">В этом примере тег `<example>` используется для включения примера использования поля `ID`.</span><span class="sxs-lookup"><span data-stu-id="18704-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="18704-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="18704-112">See also</span></span>

- [<span data-ttu-id="18704-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="18704-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
