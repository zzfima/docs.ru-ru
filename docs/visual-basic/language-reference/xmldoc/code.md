---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524035"
---
# <a name="code-visual-basic"></a><span data-ttu-id="69e37-101">> \<code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69e37-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="69e37-102">Указывает, что текст представляет собой несколько строк кода.</span><span class="sxs-lookup"><span data-stu-id="69e37-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e37-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69e37-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e37-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="69e37-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="69e37-105">Текст, помечающий как код.</span><span class="sxs-lookup"><span data-stu-id="69e37-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e37-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="69e37-106">Remarks</span></span>  
 <span data-ttu-id="69e37-107">Используйте тег `<code>`, чтобы указать несколько строк в виде кода.</span><span class="sxs-lookup"><span data-stu-id="69e37-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="69e37-108">С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="69e37-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="69e37-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="69e37-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69e37-110">Пример</span><span class="sxs-lookup"><span data-stu-id="69e37-110">Example</span></span>  
 <span data-ttu-id="69e37-111">В этом примере используется тег \<code >, чтобы добавить пример кода для использования поля `ID`.</span><span class="sxs-lookup"><span data-stu-id="69e37-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="69e37-112">См. также</span><span class="sxs-lookup"><span data-stu-id="69e37-112">See also</span></span>

- [<span data-ttu-id="69e37-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="69e37-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
