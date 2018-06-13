---
title: '#warning (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: c56458e0100c23450655e48b2abfb346e18e0bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268187"
---
# <a name="warning-c-reference"></a>#warning (справочник по C#)
`#warning` позволяет создать предупреждение первого уровня из определенного места в коде. Пример:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Примечания  
 Как правило, `#warning` применяется в условной директиве. Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.  
  
## <a name="example"></a>Пример  
  
```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
