---
title: '#error. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173410"
---
# <a name="error-c-reference"></a>#error (справочник по C#)
`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде. Пример:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Remarks  
 Как правило, `#error` применяется в условной директиве.  
  
 Кроме того, с помощью директивы [#warning](./preprocessor-warning.md) можно создать определяемое пользователем предупреждение.  
  
## <a name="example"></a>Пример  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
