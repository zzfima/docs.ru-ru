---
title: '#warning. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 08fcefd904ad43c781017087082592120e21f5cd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236834"
---
# <a name="warning-c-reference"></a>#warning (справочник по C#)
`#warning` позволяет создать предупреждение компилятора [CS1030](../../misc/cs1030.md) первого уровня из определенного места в коде. Пример:  
  
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

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
