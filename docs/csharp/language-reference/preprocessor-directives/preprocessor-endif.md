---
title: '#endif. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 58e29363ca1298966ecf88e6b456f33f43a176b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573050"
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

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
