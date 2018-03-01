---
title: "&lt;typeparam&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e1b8800e39b1ee5eeac8c5d3e4390ed3226b33a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="f9279-102">&lt;typeparam&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f9279-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f9279-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9279-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9279-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9279-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f9279-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f9279-105">The name of the type parameter.</span></span> <span data-ttu-id="f9279-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="f9279-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f9279-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f9279-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9279-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9279-108">Remarks</span></span>  
 <span data-ttu-id="f9279-109">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f9279-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="f9279-110">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="f9279-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="f9279-111">Дополнительные сведения см. в статье [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9279-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="f9279-112">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)).</span><span class="sxs-lookup"><span data-stu-id="f9279-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="f9279-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f9279-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9279-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f9279-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f9279-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f9279-115">See Also</span></span>  
 [<span data-ttu-id="f9279-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f9279-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f9279-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f9279-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f9279-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f9279-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
