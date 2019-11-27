---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e1e7f2d0fb06599f83ba224ed52a10429d9b11fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346963"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="2912a-101">> \<исключений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2912a-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="2912a-102">Указывает, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="2912a-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2912a-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2912a-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2912a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="2912a-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="2912a-105">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="2912a-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="2912a-106">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="2912a-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2912a-107">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="2912a-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2912a-108">Описание.</span><span class="sxs-lookup"><span data-stu-id="2912a-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2912a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="2912a-109">Remarks</span></span>  
 <span data-ttu-id="2912a-110">Используйте тег `<exception>`, чтобы указать, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="2912a-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="2912a-111">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="2912a-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="2912a-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="2912a-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2912a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="2912a-113">Example</span></span>  
 <span data-ttu-id="2912a-114">В этом примере используется тег `<exception>` для описания исключения, которое может вызывать функция `IntDivide`.</span><span class="sxs-lookup"><span data-stu-id="2912a-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2912a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2912a-115">See also</span></span>

- [<span data-ttu-id="2912a-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="2912a-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
