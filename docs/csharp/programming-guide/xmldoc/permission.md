---
title: '&lt;permission&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 815d303c9cfbf01588f5f2877e9f87a7ebbea9a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321481"
---
# <a name="ltpermissiongt-c-programming-guide"></a><span data-ttu-id="5c546-102">&lt;permission&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5c546-102">&lt;permission&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5c546-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c546-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c546-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c546-104">Parameters</span></span>  
 <span data-ttu-id="5c546-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="5c546-105">cref = " `member`"</span></span>  
 <span data-ttu-id="5c546-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="5c546-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5c546-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="5c546-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="5c546-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="5c546-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="5c546-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="5c546-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="5c546-110">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="5c546-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c546-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c546-111">Remarks</span></span>  
 <span data-ttu-id="5c546-112">Тег \<permission> tag позволяет документировать уровень доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="5c546-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="5c546-113">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="5c546-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="5c546-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5c546-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c546-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5c546-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5c546-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5c546-116">See Also</span></span>  
 [<span data-ttu-id="5c546-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5c546-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5c546-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5c546-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
