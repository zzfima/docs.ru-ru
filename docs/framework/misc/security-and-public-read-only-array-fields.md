---
title: Безопасность и поля-массивы с общим доступом только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03f3ce51eaab9e08d5f05932d9360adc4fd2110f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560997"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="1f2cf-102">Безопасность и поля-массивы с общим доступом только для чтения</span><span class="sxs-lookup"><span data-stu-id="1f2cf-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="1f2cf-103">Никогда не используйте поля только для чтения общих массивов из управляемых библиотек для определения поведения границы или безопасности приложений, так как открытый массива только для чтения поля можно изменять.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f2cf-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f2cf-104">Remarks</span></span>  
 <span data-ttu-id="1f2cf-105">Некоторые классы .NET framework включают только для чтения открытых полей, содержащих параметры границ для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="1f2cf-106">Например <xref:System.IO.Path.InvalidPathChars> представляет собой массив, описывающий символы, которые не разрешены в строке пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="1f2cf-107">Многие аналогичные поля, присутствуют в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="1f2cf-108">Значения открытых полей только для чтения, например <xref:System.IO.Path.InvalidPathChars> можно изменить код или код, который использует ваш код домена приложения.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="1f2cf-109">Для определения поведения границы приложений не следует использовать поля только для чтения общих массивов следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="1f2cf-110">В противном случае вредоносный код можно изменить определения границ и использовать код непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="1f2cf-111">В версии 2.0 и более поздней версии платформы .NET Framework следует использовать методы, которые возвращают новый массив, вместо использования поля открытого массивов.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="1f2cf-112">Например, вместо использования <xref:System.IO.Path.InvalidPathChars> поля, следует использовать <xref:System.IO.Path.GetInvalidPathChars%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="1f2cf-113">Обратите внимание, что типы .NET Framework не используют открытые поля для определения типов границ внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="1f2cf-114">Вместо этого .NET Framework использует отдельные закрытые поля.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="1f2cf-115">Изменение значений эти открытые поля не изменяет поведение типов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f2cf-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2cf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1f2cf-116">See also</span></span>
- [<span data-ttu-id="1f2cf-117">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="1f2cf-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
