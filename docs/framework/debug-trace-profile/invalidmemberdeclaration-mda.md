---
title: Помощник по отладке управляемого кода invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754366"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="50136-102">Помощник по отладке управляемого кода invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="50136-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="50136-103">Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.</span><span class="sxs-lookup"><span data-stu-id="50136-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="50136-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="50136-104">Symptoms</span></span>  
 <span data-ttu-id="50136-105">Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.</span><span class="sxs-lookup"><span data-stu-id="50136-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="50136-106">Причина</span><span class="sxs-lookup"><span data-stu-id="50136-106">Cause</span></span>  
 <span data-ttu-id="50136-107">Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.</span><span class="sxs-lookup"><span data-stu-id="50136-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="50136-108">Решение</span><span class="sxs-lookup"><span data-stu-id="50136-108">Resolution</span></span>  
 <span data-ttu-id="50136-109">Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.</span><span class="sxs-lookup"><span data-stu-id="50136-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="50136-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="50136-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="50136-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="50136-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="50136-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="50136-112">Output</span></span>  
 <span data-ttu-id="50136-113">Информационное сообщение с именем члена, именем типа и сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="50136-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="50136-114">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="50136-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50136-115">См. также</span><span class="sxs-lookup"><span data-stu-id="50136-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="50136-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="50136-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="50136-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="50136-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
