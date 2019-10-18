---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 16ffb4f6b57dabb3650376c913a7d7608a00646d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523930"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="9c228-102">> \<exception (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c228-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="9c228-103">Указывает, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="9c228-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c228-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c228-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c228-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c228-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="9c228-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="9c228-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="9c228-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="9c228-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="9c228-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="9c228-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9c228-109">Описание.</span><span class="sxs-lookup"><span data-stu-id="9c228-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c228-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="9c228-110">Remarks</span></span>  
 <span data-ttu-id="9c228-111">Используйте тег `<exception>`, чтобы указать, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="9c228-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="9c228-112">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="9c228-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="9c228-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="9c228-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c228-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9c228-114">Example</span></span>  
 <span data-ttu-id="9c228-115">В этом примере используется тег `<exception>` для описания исключения, которое может вызывать функция `IntDivide`.</span><span class="sxs-lookup"><span data-stu-id="9c228-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9c228-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9c228-116">See also</span></span>

- [<span data-ttu-id="9c228-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="9c228-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
