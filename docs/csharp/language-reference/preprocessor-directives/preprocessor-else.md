---
title: '#else (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 000cbaac4458a104214e3197442a21dcb4740a37
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530228"
---
# <a name="else-c-reference"></a>#else (Справочник по C#)
С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или (необязательно) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.  
  
## <a name="remarks"></a>Примечания  
 Директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`. В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#else`.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
