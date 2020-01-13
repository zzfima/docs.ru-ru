---
title: '#error. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 7203e1271da66e78bfbd70717b0f5e536a7ebd86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712524"
---
# <a name="error-c-reference"></a>#error (справочник по C#)
`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде. Пример:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Примечания  
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
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
