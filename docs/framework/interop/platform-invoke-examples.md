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
# <a name="platform-invoke-examples"></a>Примеры вызовов неуправляемого кода
В следующих примерах демонстрируется, как определить и вызвать функцию **MessageBox** в User32.dll, передав в качестве аргумента простую строку. В этом примере полю <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> присваивается значение **Автоматически**, благодаря чему целевая платформа определяет ширину символа и параметры маршалинга строк.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Дополнительные примеры см. в разделе [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Создание прототипов в управляемом коде](creating-prototypes-in-managed-code.md)
- [Определение кодировки](specifying-a-character-set.md)
