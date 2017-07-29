---
title: "#<a name=\"region-c-reference\"></a>region (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
dev_langs:
- CSharp
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7685d23bc1d40a0d0b6c9ac9a644019e1186eb7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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

