---
title: '#endif. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 13b43919b666dcc8c5adfc3490eaad73960547ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243911"
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
