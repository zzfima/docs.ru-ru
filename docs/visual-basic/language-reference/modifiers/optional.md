---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: f88020c7407fb9c91e06bc2ee177773171e344fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.  
  
## <a name="remarks"></a>Примечания  
 Для каждого необязательного параметра как значение по умолчанию этого параметра необходимо указать константное выражение. Если выражение, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), значение по умолчанию для типа данных значение используется как значение параметра по умолчанию.  
  
 Если список параметров содержит дополнительный параметр, каждый параметр, следующий за ним также должен быть необязательным.  
  
 Модификатор `Optional` можно использовать в следующих контекстах:  
  
-   [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  При вызове процедуры с или без необязательных параметров, аргументы можно передать по положению или по имени. Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Можно также определить процедуры с необязательными параметрами с помощью перегрузки. Если у вас есть один необязательный параметр, можно определить две перегруженные версии процедуры, принимающую параметр, а другой не. Дополнительные сведения см. в разделе [перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Пример  
 В следующем примере определяется процедуру, которая принимает необязательный параметр.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует вызов процедуры с аргументы, передаваемые по позиции и с аргументами, передаваемыми по имени. Процедура включает два необязательных параметра.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
