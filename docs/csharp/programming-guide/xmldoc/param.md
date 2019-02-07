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
ms.openlocfilehash: 3f1099da6a43ed7f48389a16e3be6a3b6b98a148
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271581"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="f5c66-102">\<param> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f5c66-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f5c66-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5c66-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5c66-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5c66-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f5c66-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="f5c66-105">The name of a method parameter.</span></span> <span data-ttu-id="f5c66-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="f5c66-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f5c66-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="f5c66-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5c66-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5c66-108">Remarks</span></span>  
 <span data-ttu-id="f5c66-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="f5c66-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="f5c66-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="f5c66-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="f5c66-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="f5c66-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="f5c66-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f5c66-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5c66-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f5c66-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f5c66-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f5c66-114">See also</span></span>

- [<span data-ttu-id="f5c66-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f5c66-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f5c66-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f5c66-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
