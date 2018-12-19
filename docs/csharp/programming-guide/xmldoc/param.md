---
title: Руководство по программированию на C#. Тег &lt;param&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: fca53a3cd5490c28c8fabcf69446fe4a55d60b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236964"
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="c7c64-102">&lt;param&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c7c64-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c7c64-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7c64-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7c64-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7c64-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c7c64-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="c7c64-105">The name of a method parameter.</span></span> <span data-ttu-id="c7c64-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="c7c64-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c7c64-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="c7c64-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7c64-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7c64-108">Remarks</span></span>  
 <span data-ttu-id="c7c64-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="c7c64-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="c7c64-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="c7c64-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="c7c64-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="c7c64-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="c7c64-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c7c64-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c64-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c7c64-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c7c64-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c7c64-114">See Also</span></span>

- [<span data-ttu-id="c7c64-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c7c64-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c7c64-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="c7c64-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
