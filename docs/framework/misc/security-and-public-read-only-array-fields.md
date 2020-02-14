---
title: Безопасность и поля-массивы с общим доступом только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 215e8136b4bc3f2982cdb2d8382b0eca6a881f9b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217034"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="52340-102">Безопасность и поля-массивы с общим доступом только для чтения</span><span class="sxs-lookup"><span data-stu-id="52340-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="52340-103">Никогда не используйте открытые поля только для чтения из управляемых библиотек, чтобы определить поведение границ или безопасность приложений, поскольку можно изменять открытые поля массива, предназначенные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="52340-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52340-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="52340-104">Remarks</span></span>  
 <span data-ttu-id="52340-105">Некоторые классы .NET Framework содержат открытые поля только для чтения, содержащие параметры границ для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="52340-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="52340-106">Например, поле <xref:System.IO.Path.InvalidPathChars> представляет собой массив, описывающий символы, которые не допускаются в строке пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="52340-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="52340-107">Во всех .NET Framework имеются похожие поля.</span><span class="sxs-lookup"><span data-stu-id="52340-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="52340-108">Значения открытых полей только для чтения, таких как <xref:System.IO.Path.InvalidPathChars>, могут быть изменены кодом или кодом, который использует домен приложения вашего кода.</span><span class="sxs-lookup"><span data-stu-id="52340-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="52340-109">Не следует использовать открытые поля только для чтения, например, для определения поведения приложений в границах.</span><span class="sxs-lookup"><span data-stu-id="52340-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="52340-110">В противном случае вредоносный код может изменить определения границ и использовать код непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="52340-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="52340-111">В версии 2,0 и более поздних .NET Framework следует использовать методы, возвращающие новый массив, вместо использования полей открытого массива.</span><span class="sxs-lookup"><span data-stu-id="52340-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="52340-112">Например, вместо использования поля <xref:System.IO.Path.InvalidPathChars> следует использовать метод <xref:System.IO.Path.GetInvalidPathChars%2A>.</span><span class="sxs-lookup"><span data-stu-id="52340-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="52340-113">Обратите внимание, что типы .NET Framework не используют открытые поля для внутреннего определения типов границ.</span><span class="sxs-lookup"><span data-stu-id="52340-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="52340-114">Вместо этого в .NET Framework используются отдельные закрытые поля.</span><span class="sxs-lookup"><span data-stu-id="52340-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="52340-115">Изменение значений этих открытых полей не влияет на поведение типов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52340-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52340-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="52340-116">See also</span></span>

- [<span data-ttu-id="52340-117">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="52340-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
