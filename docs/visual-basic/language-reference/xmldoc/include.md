---
title: "&lt;включить&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="9a568-102">&lt;включить&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a568-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="9a568-103">Ссылается на другой файл, описывающий типы и члены в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="9a568-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a568-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a568-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a568-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a568-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="9a568-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9a568-106">Required.</span></span> <span data-ttu-id="9a568-107">Имя файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="9a568-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="9a568-108">Имя файла может быть дополнено с указанием пути.</span><span class="sxs-lookup"><span data-stu-id="9a568-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="9a568-109">Заключите `filename` в двойные кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="9a568-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="9a568-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9a568-110">Required.</span></span> <span data-ttu-id="9a568-111">Путь тегов в `filename`, который ведет к тегу `name`.</span><span class="sxs-lookup"><span data-stu-id="9a568-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="9a568-112">Заключите путь в двойные кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="9a568-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="9a568-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9a568-113">Required.</span></span> <span data-ttu-id="9a568-114">Спецификатор имени тега, который предшествует комментарии.</span><span class="sxs-lookup"><span data-stu-id="9a568-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="9a568-115">`Name`будет иметь `id`.</span><span class="sxs-lookup"><span data-stu-id="9a568-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="9a568-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9a568-116">Required.</span></span> <span data-ttu-id="9a568-117">Идентификатор тега, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="9a568-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="9a568-118">Заключите идентификатор в одинарные кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="9a568-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a568-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a568-119">Remarks</span></span>  
 <span data-ttu-id="9a568-120">Используйте `<include>` тег для ссылок на комментарии в другом файле, описывающем типы и элементы в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="9a568-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="9a568-121">Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="9a568-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="9a568-122">`<include>` Тег использует рекомендация W3C языка XML Path (XPath) версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="9a568-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="9a568-123">Дополнительные сведения о способах настройки вашей `<include>` используйте найти по адресу http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="9a568-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a568-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9a568-124">Example</span></span>  
 <span data-ttu-id="9a568-125">В этом примере используется `<include>` тег, чтобы импортировать член комментарии из файла с именем `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="9a568-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="9a568-126">Формат `commentFile.xml` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a568-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a568-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9a568-127">See Also</span></span>  
 [<span data-ttu-id="9a568-128">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="9a568-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
