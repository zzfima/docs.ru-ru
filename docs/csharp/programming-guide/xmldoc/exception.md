---
title: <exception> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: fe304b9c6631591cf7a3d62fcecd2ed3ca05db9c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257295"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="97680-102">\<exception> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="97680-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="97680-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97680-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97680-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="97680-104">Parameters</span></span>  
 <span data-ttu-id="97680-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="97680-105">cref = " `member`"</span></span>  
 <span data-ttu-id="97680-106">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="97680-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="97680-107">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="97680-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="97680-108">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="97680-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="97680-109">Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="97680-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="97680-110">Описание исключения.</span><span class="sxs-lookup"><span data-stu-id="97680-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97680-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="97680-111">Remarks</span></span>  
 <span data-ttu-id="97680-112">Тег \<exception> служит для указания возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="97680-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="97680-113">Этот тег может применяться к определениям методов, свойств, событий и индексаторов.</span><span class="sxs-lookup"><span data-stu-id="97680-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="97680-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="97680-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="97680-115">Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="97680-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97680-116">Пример</span><span class="sxs-lookup"><span data-stu-id="97680-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="97680-117">См. также</span><span class="sxs-lookup"><span data-stu-id="97680-117">See also</span></span>

- [<span data-ttu-id="97680-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="97680-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="97680-119">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="97680-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
