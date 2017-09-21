---
title: "#<a name=\"error-c-reference\"></a>error (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
dev_langs:
- CSharp
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
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
ms.openlocfilehash: d2d497d7b8345b94dfc77176bf2b0ca79674e9be
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="error-c-reference"></a>#error (справочник по C#)
`#error` позволяет создать ошибку из определенного места в коде. Пример:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Примечания  
 Как правило, `#error` применяется в условной директиве.  
  
 Кроме того, с помощью директивы [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) можно создать определяемое пользователем предупреждение.  
  
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
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)

