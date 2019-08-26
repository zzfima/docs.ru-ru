---
title: '#region. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ba5b47d77c69761a77b05ac6079e1b003af336b3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608754"
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
 В конце блока `#region` должна присутствовать директива [#endregion](./preprocessor-endregion.md).  
  
 Блок `#region` не может накладываться на блок [#if](./preprocessor-if.md). Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
