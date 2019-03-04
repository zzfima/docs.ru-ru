---
title: <param> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 08b5257cedfcaf6fe34b8218dda93163d4c0d98b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976686"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="4af59-102">\<param> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4af59-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4af59-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4af59-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4af59-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="4af59-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4af59-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="4af59-105">The name of a method parameter.</span></span> <span data-ttu-id="4af59-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="4af59-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="4af59-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="4af59-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af59-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4af59-108">Remarks</span></span>  
 <span data-ttu-id="4af59-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="4af59-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="4af59-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="4af59-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="4af59-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="4af59-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="4af59-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4af59-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af59-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4af59-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4af59-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4af59-114">See also</span></span>

- [<span data-ttu-id="4af59-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4af59-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4af59-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4af59-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
