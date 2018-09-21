---
title: '&lt;включить&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531909"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="ebb68-102">&lt;включить&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebb68-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="ebb68-103">Ссылается на другой файл, который описывает типы и члены в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="ebb68-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebb68-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebb68-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebb68-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="ebb68-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ebb68-106">Required.</span></span> <span data-ttu-id="ebb68-107">Имя файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="ebb68-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="ebb68-108">Имя файла может быть дополнено с указанием пути.</span><span class="sxs-lookup"><span data-stu-id="ebb68-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="ebb68-109">Заключите `filename` в двойные кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="ebb68-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="ebb68-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ebb68-110">Required.</span></span> <span data-ttu-id="ebb68-111">Путь тегов в `filename`, который ведет к тегу `name`.</span><span class="sxs-lookup"><span data-stu-id="ebb68-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="ebb68-112">Заключите путь в двойные кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="ebb68-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="ebb68-113">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ebb68-113">Required.</span></span> <span data-ttu-id="ebb68-114">Спецификатор имени в теге, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="ebb68-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="ebb68-115">`Name` будет иметь `id`.</span><span class="sxs-lookup"><span data-stu-id="ebb68-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="ebb68-116">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ebb68-116">Required.</span></span> <span data-ttu-id="ebb68-117">Идентификатор тега, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="ebb68-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="ebb68-118">Идентификатор заключается в одинарные кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="ebb68-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebb68-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebb68-119">Remarks</span></span>  
 <span data-ttu-id="ebb68-120">Используйте `<include>` тег для ссылки на комментарии в другом файле, описывающем типы и члены в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="ebb68-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="ebb68-121">Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="ebb68-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="ebb68-122">`<include>` Тег использует в соответствии с рекомендацией W3C XML Path Language (XPath) версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="ebb68-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="ebb68-123">Дополнительные сведения о способах настройки вашего `<include>` доступен в http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="ebb68-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb68-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ebb68-124">Example</span></span>  
 <span data-ttu-id="ebb68-125">В этом примере используется `<include>` тег для импорта из файла с именем члена комментарии к документации `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="ebb68-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="ebb68-126">Формат `commentFile.xml` выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ebb68-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ebb68-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ebb68-127">See Also</span></span>  
 [<span data-ttu-id="ebb68-128">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="ebb68-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
