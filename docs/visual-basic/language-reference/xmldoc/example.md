---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f28dbf19bc03cb9d91323e9fa43a7081c1990db
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524004"
---
# <a name="example-visual-basic"></a><span data-ttu-id="08a81-102">> \<example (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08a81-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="08a81-103">Указывает пример для элемента.</span><span class="sxs-lookup"><span data-stu-id="08a81-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08a81-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08a81-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="08a81-106">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="08a81-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08a81-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="08a81-107">Remarks</span></span>  
 <span data-ttu-id="08a81-108">Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="08a81-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="08a81-109">Вместе с ним часто применяется тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="08a81-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="08a81-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="08a81-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08a81-111">Пример</span><span class="sxs-lookup"><span data-stu-id="08a81-111">Example</span></span>  
 <span data-ttu-id="08a81-112">В этом примере тег `<example>` используется для включения примера использования поля `ID`.</span><span class="sxs-lookup"><span data-stu-id="08a81-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="08a81-113">См. также</span><span class="sxs-lookup"><span data-stu-id="08a81-113">See also</span></span>

- [<span data-ttu-id="08a81-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="08a81-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
