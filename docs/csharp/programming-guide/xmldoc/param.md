---
title: "&lt;param&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a5325b91130623442c9cf5453e52418bb44cc34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="f1d08-102">&lt;param&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f1d08-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f1d08-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1d08-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1d08-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1d08-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f1d08-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="f1d08-105">The name of a method parameter.</span></span> <span data-ttu-id="f1d08-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="f1d08-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f1d08-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="f1d08-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d08-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1d08-108">Remarks</span></span>  
 <span data-ttu-id="f1d08-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="f1d08-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="f1d08-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="f1d08-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="f1d08-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="f1d08-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="f1d08-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f1d08-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1d08-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f1d08-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f1d08-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d08-114">See Also</span></span>  
 [<span data-ttu-id="f1d08-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f1d08-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f1d08-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f1d08-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
