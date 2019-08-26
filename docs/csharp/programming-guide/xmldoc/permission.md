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
ms.openlocfilehash: e9eb50394f01072a194d3f746577707f89ba65dd
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587880"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="1904f-102">\<permission> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1904f-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="1904f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1904f-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1904f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1904f-104">Parameters</span></span>  
 <span data-ttu-id="1904f-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="1904f-105">cref = " `member`"</span></span>  
 <span data-ttu-id="1904f-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="1904f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="1904f-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="1904f-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="1904f-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="1904f-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="1904f-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="1904f-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="1904f-110">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="1904f-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1904f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1904f-111">Remarks</span></span>  
 <span data-ttu-id="1904f-112">Тег \<permission> tag позволяет документировать уровень доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="1904f-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="1904f-113">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="1904f-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="1904f-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1904f-114">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1904f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1904f-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="1904f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1904f-116">See also</span></span>

- [<span data-ttu-id="1904f-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1904f-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1904f-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="1904f-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
