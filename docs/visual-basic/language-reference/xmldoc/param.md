---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c62eab6b1fb1ba1cc7de83c12d7205cf0bbe46fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524730"
---
# <a name="param-visual-basic"></a><span data-ttu-id="d07fa-102">> \<param (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d07fa-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="d07fa-103">Определяет имя и описание параметра.</span><span class="sxs-lookup"><span data-stu-id="d07fa-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d07fa-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d07fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d07fa-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d07fa-106">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="d07fa-106">The name of a method parameter.</span></span> <span data-ttu-id="d07fa-107">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="d07fa-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d07fa-108">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="d07fa-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d07fa-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d07fa-109">Remarks</span></span>  
 <span data-ttu-id="d07fa-110">Тег `<param>` должен использоваться в комментариях для объявления метода, чтобы описать один из параметров для метода.</span><span class="sxs-lookup"><span data-stu-id="d07fa-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="d07fa-111">Текст тега `<param>` будет отображаться в следующих расположениях:</span><span class="sxs-lookup"><span data-stu-id="d07fa-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="d07fa-112">Сведения о параметрах IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d07fa-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="d07fa-113">Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="d07fa-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="d07fa-114">Обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="d07fa-114">Object Browser.</span></span> <span data-ttu-id="d07fa-115">Дополнительные сведения см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="d07fa-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="d07fa-116">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d07fa-116">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d07fa-117">Пример</span><span class="sxs-lookup"><span data-stu-id="d07fa-117">Example</span></span>  
 <span data-ttu-id="d07fa-118">В этом примере используется тег `<param>` для описания параметра `id`.</span><span class="sxs-lookup"><span data-stu-id="d07fa-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d07fa-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d07fa-119">See also</span></span>

- [<span data-ttu-id="d07fa-120">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d07fa-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
