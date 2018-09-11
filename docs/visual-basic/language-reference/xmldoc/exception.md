---
title: '&lt;исключение&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337698"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="c1e72-102">&lt;исключение&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1e72-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="c1e72-103">Указывает, какие исключения могут вызываться.</span><span class="sxs-lookup"><span data-stu-id="c1e72-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1e72-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1e72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1e72-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c1e72-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="c1e72-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c1e72-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c1e72-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c1e72-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="c1e72-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c1e72-109">Описание.</span><span class="sxs-lookup"><span data-stu-id="c1e72-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1e72-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1e72-110">Remarks</span></span>  
 <span data-ttu-id="c1e72-111">Используйте `<exception>` тег, чтобы указать, какие исключения могут вызываться.</span><span class="sxs-lookup"><span data-stu-id="c1e72-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="c1e72-112">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="c1e72-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="c1e72-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c1e72-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1e72-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c1e72-114">Example</span></span>  
 <span data-ttu-id="c1e72-115">В этом примере используется `<exception>` тегов для описания исключения, `IntDivide` может создавать функция.</span><span class="sxs-lookup"><span data-stu-id="c1e72-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c1e72-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c1e72-116">See Also</span></span>  
 [<span data-ttu-id="c1e72-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="c1e72-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
