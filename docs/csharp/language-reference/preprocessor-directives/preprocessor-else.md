---
title: "#<a name=\"else-c-reference\"></a>else (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#else'
dev_langs:
- CSharp
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: 11
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
ms.openlocfilehash: c4b593c757180af22ce512be624e9ac94a2e1bc6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="else-c-reference"></a>#else (Справочник по C#)
С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или (необязательно) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.  
  
## <a name="remarks"></a>Примечания  
 Директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`. В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#else`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)

