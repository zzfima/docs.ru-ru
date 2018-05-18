---
title: '#endif (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 1686e706ce5cae3b2eaa28a7e1c89b5694b2be88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endif-c-reference"></a>#endif (Справочник по C#)
`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Например, примененная к объекту директива  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Примечания  
 Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`. В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#endif`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
