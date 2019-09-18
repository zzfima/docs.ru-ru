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
ms.openlocfilehash: fe15d718a9c5f91bfae4f37c04e726990e2fbd45
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052584"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="20ed1-102">Помощник по отладке управляемого кода invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="20ed1-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="20ed1-103">Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.</span><span class="sxs-lookup"><span data-stu-id="20ed1-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="20ed1-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="20ed1-104">Symptoms</span></span>  
 <span data-ttu-id="20ed1-105">Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.</span><span class="sxs-lookup"><span data-stu-id="20ed1-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="20ed1-106">Причина</span><span class="sxs-lookup"><span data-stu-id="20ed1-106">Cause</span></span>  
 <span data-ttu-id="20ed1-107">Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.</span><span class="sxs-lookup"><span data-stu-id="20ed1-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="20ed1-108">Решение</span><span class="sxs-lookup"><span data-stu-id="20ed1-108">Resolution</span></span>  
 <span data-ttu-id="20ed1-109">Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.</span><span class="sxs-lookup"><span data-stu-id="20ed1-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="20ed1-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="20ed1-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="20ed1-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="20ed1-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="20ed1-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="20ed1-112">Output</span></span>  
 <span data-ttu-id="20ed1-113">Информационное сообщение с именем члена, именем типа и сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="20ed1-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="20ed1-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="20ed1-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20ed1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="20ed1-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="20ed1-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="20ed1-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="20ed1-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="20ed1-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
