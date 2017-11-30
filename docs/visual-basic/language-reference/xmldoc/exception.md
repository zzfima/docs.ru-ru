---
title: "&lt;исключение&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d718a7c2213a61f7f60ed80a04f9bd03f6c770a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="0aa72-102">&lt;исключение&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aa72-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="0aa72-103">Указывает, какие исключения.</span><span class="sxs-lookup"><span data-stu-id="0aa72-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aa72-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0aa72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0aa72-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="0aa72-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="0aa72-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="0aa72-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="0aa72-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="0aa72-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="0aa72-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="0aa72-109">Описание.</span><span class="sxs-lookup"><span data-stu-id="0aa72-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aa72-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0aa72-110">Remarks</span></span>  
 <span data-ttu-id="0aa72-111">Используйте `<exception>` тег, чтобы указать, какие исключения.</span><span class="sxs-lookup"><span data-stu-id="0aa72-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="0aa72-112">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="0aa72-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="0aa72-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="0aa72-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aa72-114">Пример</span><span class="sxs-lookup"><span data-stu-id="0aa72-114">Example</span></span>  
 <span data-ttu-id="0aa72-115">В этом примере используется `<exception>` тегов для описания исключения, `IntDivide` функция может создавать.</span><span class="sxs-lookup"><span data-stu-id="0aa72-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0aa72-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0aa72-116">See Also</span></span>  
 [<span data-ttu-id="0aa72-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="0aa72-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
