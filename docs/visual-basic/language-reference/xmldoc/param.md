---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 476b3f4f6b85908897e15f73bc23d2b060e337c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283651"
---
# <a name="param-visual-basic"></a><span data-ttu-id="82b8a-102">\<PARAM > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b8a-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="82b8a-103">Определяет имя параметра и описание.</span><span class="sxs-lookup"><span data-stu-id="82b8a-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82b8a-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82b8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="82b8a-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="82b8a-106">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="82b8a-106">The name of a method parameter.</span></span> <span data-ttu-id="82b8a-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="82b8a-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="82b8a-108">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="82b8a-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82b8a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="82b8a-109">Remarks</span></span>  
 <span data-ttu-id="82b8a-110">`<param>` Тегов следует использовать в комментариях к объявлению метода для описания одного из параметров для метода.</span><span class="sxs-lookup"><span data-stu-id="82b8a-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="82b8a-111">Текст для `<param>` тег будет отображаться в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="82b8a-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="82b8a-112">Сведения о параметрах из IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="82b8a-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="82b8a-113">Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="82b8a-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="82b8a-114">Обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="82b8a-114">Object Browser.</span></span> <span data-ttu-id="82b8a-115">Дополнительные сведения см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="82b8a-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="82b8a-116">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="82b8a-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b8a-117">Пример</span><span class="sxs-lookup"><span data-stu-id="82b8a-117">Example</span></span>  
 <span data-ttu-id="82b8a-118">В этом примере используется `<param>` тегов для описания `id` параметра.</span><span class="sxs-lookup"><span data-stu-id="82b8a-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="82b8a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="82b8a-119">See also</span></span>
- [<span data-ttu-id="82b8a-120">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="82b8a-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
