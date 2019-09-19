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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89c2043570b9e2798ef41984b889791ddfe1d526
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051665"
---
# <a name="platform-invoke-examples"></a>Примеры вызовов неуправляемого кода
В следующих примерах демонстрируется, как определить и вызвать функцию **MessageBox** в User32.dll, передав в качестве аргумента простую строку. В этом примере полю <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> присваивается значение **Автоматически**, благодаря чему целевая платформа определяет ширину символа и параметры маршалинга строк.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Дополнительные примеры см. в разделе [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Создание прототипов в управляемом коде](creating-prototypes-in-managed-code.md)
- [Определение кодировки](specifying-a-character-set.md)
