---
title: "Примеры вызовов неуправляемого кода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec8f261ab6f6f8b0c57f302859e1212d237b12aa
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="platform-invoke-examples"></a>Примеры вызовов неуправляемого кода
В следующих примерах демонстрируется, как определить и вызвать функцию **MessageBox** в User32.dll, передав в качестве аргумента простую строку. В этом примере полю <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> присваивается значение **Автоматически**, благодаря чему целевая платформа определяет ширину символа и параметры маршалинга строк.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]   
  
 Дополнительные примеры см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Определение кодировки](../../../docs/framework/interop/specifying-a-character-set.md)

