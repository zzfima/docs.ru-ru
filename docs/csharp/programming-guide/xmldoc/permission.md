---
title: <permission> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 475e9ab5c59260544b0e413e165953c0b84449b5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973903"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="b6f28-102">\<permission> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b6f28-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b6f28-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6f28-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6f28-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6f28-104">Parameters</span></span>  
 <span data-ttu-id="b6f28-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="b6f28-105">cref = " `member`"</span></span>  
 <span data-ttu-id="b6f28-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="b6f28-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b6f28-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b6f28-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b6f28-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="b6f28-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="b6f28-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="b6f28-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="b6f28-110">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="b6f28-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6f28-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6f28-111">Remarks</span></span>  
 <span data-ttu-id="b6f28-112">Тег \<permission> tag позволяет документировать уровень доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="b6f28-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="b6f28-113">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="b6f28-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="b6f28-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6f28-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6f28-115">Пример</span><span class="sxs-lookup"><span data-stu-id="b6f28-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="b6f28-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b6f28-116">See also</span></span>

- [<span data-ttu-id="b6f28-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b6f28-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b6f28-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="b6f28-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
