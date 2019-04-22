---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 4e2f441863d6a8677593a257cdb2cc841634d47c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820247"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="2b45f-102">\<исключение > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b45f-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="2b45f-103">Указывает, какие исключения могут вызываться.</span><span class="sxs-lookup"><span data-stu-id="2b45f-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b45f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b45f-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b45f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b45f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="2b45f-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="2b45f-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="2b45f-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="2b45f-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2b45f-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="2b45f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2b45f-109">Описание.</span><span class="sxs-lookup"><span data-stu-id="2b45f-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b45f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b45f-110">Remarks</span></span>  
 <span data-ttu-id="2b45f-111">Используйте `<exception>` тег, чтобы указать, какие исключения могут вызываться.</span><span class="sxs-lookup"><span data-stu-id="2b45f-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="2b45f-112">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="2b45f-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="2b45f-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="2b45f-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b45f-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2b45f-114">Example</span></span>  
 <span data-ttu-id="2b45f-115">В этом примере используется `<exception>` тегов для описания исключения, `IntDivide` может создавать функция.</span><span class="sxs-lookup"><span data-stu-id="2b45f-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2b45f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2b45f-116">See also</span></span>

- [<span data-ttu-id="2b45f-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="2b45f-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
