---
title: Примеры вызовов неуправляемого кода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 358d1ce662d56b8c31124f4b3264ec25a0f94586
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181320"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="1a895-102">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="1a895-102">Platform Invoke Examples</span></span>
<span data-ttu-id="1a895-103">В следующих примерах демонстрируется, как определить и вызвать функцию **MessageBox** в User32.dll, передав в качестве аргумента простую строку.</span><span class="sxs-lookup"><span data-stu-id="1a895-103">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="1a895-104">В этом примере полю <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> присваивается значение **Автоматически**, благодаря чему целевая платформа определяет ширину символа и параметры маршалинга строк.</span><span class="sxs-lookup"><span data-stu-id="1a895-104">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="1a895-105">Дополнительные примеры см. в разделе [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="1a895-105">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a895-106">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a895-106">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="1a895-107">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="1a895-107">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="1a895-108">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="1a895-108">Specifying a Character Set</span></span>](specifying-a-character-set.md)
