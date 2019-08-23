---
title: Безопасность и поля-массивы с общим доступом только для чтения
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910740"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="3e617-102">Безопасность и поля-массивы с общим доступом только для чтения</span><span class="sxs-lookup"><span data-stu-id="3e617-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="3e617-103">Никогда не используйте открытые поля только для чтения из управляемых библиотек, чтобы определить поведение границ или безопасность приложений, поскольку можно изменять открытые поля массива, предназначенные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3e617-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e617-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e617-104">Remarks</span></span>  
 <span data-ttu-id="3e617-105">Некоторые классы .NET Framework содержат открытые поля только для чтения, содержащие параметры границ для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="3e617-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="3e617-106">Например, <xref:System.IO.Path.InvalidPathChars> поле представляет собой массив, описывающий символы, которые не допускаются в строке пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="3e617-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="3e617-107">Во всех .NET Framework имеются похожие поля.</span><span class="sxs-lookup"><span data-stu-id="3e617-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="3e617-108">Значения открытых полей только для чтения, например <xref:System.IO.Path.InvalidPathChars> , могут быть изменены кодом или кодом, который использует домен приложения вашего кода.</span><span class="sxs-lookup"><span data-stu-id="3e617-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="3e617-109">Не следует использовать открытые поля только для чтения, например, для определения поведения приложений в границах.</span><span class="sxs-lookup"><span data-stu-id="3e617-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="3e617-110">В противном случае вредоносный код может изменить определения границ и использовать код непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="3e617-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="3e617-111">В версии 2,0 и более поздних .NET Framework следует использовать методы, возвращающие новый массив, вместо использования полей открытого массива.</span><span class="sxs-lookup"><span data-stu-id="3e617-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="3e617-112">Например, вместо использования <xref:System.IO.Path.InvalidPathChars> поля следует <xref:System.IO.Path.GetInvalidPathChars%2A> использовать метод.</span><span class="sxs-lookup"><span data-stu-id="3e617-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="3e617-113">Обратите внимание, что типы .NET Framework не используют открытые поля для внутреннего определения типов границ.</span><span class="sxs-lookup"><span data-stu-id="3e617-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="3e617-114">Вместо этого в .NET Framework используются отдельные закрытые поля.</span><span class="sxs-lookup"><span data-stu-id="3e617-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="3e617-115">Изменение значений этих открытых полей не влияет на поведение типов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e617-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e617-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3e617-116">See also</span></span>

- [<span data-ttu-id="3e617-117">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="3e617-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
