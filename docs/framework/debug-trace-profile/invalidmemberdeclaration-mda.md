---
title: "Помощник по отладке управляемого кода invalidMemberDeclaration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71313a14ba1f9222e19dbf9f8180280d0e8c444d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="0880f-102">Помощник по отладке управляемого кода invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="0880f-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="0880f-103">Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.</span><span class="sxs-lookup"><span data-stu-id="0880f-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0880f-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="0880f-104">Symptoms</span></span>  
 <span data-ttu-id="0880f-105">Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.</span><span class="sxs-lookup"><span data-stu-id="0880f-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0880f-106">Причина</span><span class="sxs-lookup"><span data-stu-id="0880f-106">Cause</span></span>  
 <span data-ttu-id="0880f-107">Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.</span><span class="sxs-lookup"><span data-stu-id="0880f-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0880f-108">Решение</span><span class="sxs-lookup"><span data-stu-id="0880f-108">Resolution</span></span>  
 <span data-ttu-id="0880f-109">Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.</span><span class="sxs-lookup"><span data-stu-id="0880f-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0880f-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="0880f-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="0880f-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="0880f-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0880f-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="0880f-112">Output</span></span>  
 <span data-ttu-id="0880f-113">Информационное сообщение с именем члена, именем типа и сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0880f-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0880f-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0880f-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0880f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0880f-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0880f-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="0880f-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="0880f-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="0880f-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
