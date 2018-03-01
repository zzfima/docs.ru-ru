---
title: "#region (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce4a8ac79c4687280e28618d8863d16cd193a3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="region-c-reference"></a>#region (Справочник по C#)
Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода Visual Studio. В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа. В следующем примере показано, как определить область:  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Примечания  
 В конце блока `#region` должна присутствовать директива [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).  
  
 Блок `#region` не может накладываться на блок [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
