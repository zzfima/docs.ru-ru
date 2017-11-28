---
title: "&lt;permission&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37bb37ea14edc1f91225f9b04b18b354d99579b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="656f6-102">&lt;permission&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="656f6-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="656f6-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="656f6-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="656f6-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="656f6-104">Parameters</span></span>  
 <span data-ttu-id="656f6-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="656f6-105">cref = " `member`"</span></span>  
 <span data-ttu-id="656f6-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="656f6-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="656f6-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="656f6-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="656f6-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="656f6-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="656f6-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="656f6-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="656f6-110">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="656f6-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="656f6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="656f6-111">Remarks</span></span>  
 <span data-ttu-id="656f6-112">Тег \<permission> tag позволяет документировать уровень доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="656f6-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="656f6-113">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="656f6-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="656f6-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="656f6-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="656f6-115">Пример</span><span class="sxs-lookup"><span data-stu-id="656f6-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="656f6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="656f6-116">See Also</span></span>  
 [<span data-ttu-id="656f6-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="656f6-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="656f6-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="656f6-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
