---
title: "&lt;PARAM&gt; (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: ddf5baf83816d757edf67cdf1c66dc24e4313b83
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="7b123-102">&lt;PARAM&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b123-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="7b123-103">Определяет имя параметра и описание.</span><span class="sxs-lookup"><span data-stu-id="7b123-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b123-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b123-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b123-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b123-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7b123-106">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="7b123-106">The name of a method parameter.</span></span> <span data-ttu-id="7b123-107">Заключите имя в двойные кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="7b123-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="7b123-108">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="7b123-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b123-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b123-109">Remarks</span></span>  
 <span data-ttu-id="7b123-110">`<param>` Тегов следует использовать в комментариях объявления метода для описания параметров для метода.</span><span class="sxs-lookup"><span data-stu-id="7b123-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="7b123-111">Текст для `<param>` тег будет отображаться в следующих местах:</span><span class="sxs-lookup"><span data-stu-id="7b123-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="7b123-112">Сведения о параметрах технологии IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7b123-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="7b123-113">Дополнительные сведения см. в статье [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) (Использование IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="7b123-113">For more information, see [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="7b123-114">Обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="7b123-114">Object Browser.</span></span> <span data-ttu-id="7b123-115">Дополнительные сведения см. в разделе [Просмотр структуры кода](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="7b123-115">For more information, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="7b123-116">Скомпилируйте с [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) чтобы обработать комментарии документации в файл.</span><span class="sxs-lookup"><span data-stu-id="7b123-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b123-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7b123-117">Example</span></span>  
 <span data-ttu-id="7b123-118">В этом примере используется `<param>` тегов для описания `id` параметр.</span><span class="sxs-lookup"><span data-stu-id="7b123-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 <span data-ttu-id="7b123-119">[!code-vb[VbVbcnXmlDocComments №&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b123-119">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b123-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7b123-120">See Also</span></span>  
 [<span data-ttu-id="7b123-121">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="7b123-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
