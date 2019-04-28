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
ms.openlocfilehash: 67ceedffecdfba8ec0c2829a3af31d194f18bd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920670"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.  
  
## <a name="remarks"></a>Примечания  
 Для каждого необязательного параметра как значение по умолчанию этого параметра необходимо указать константное выражение. Если выражение, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), как значение параметра по умолчанию используется значение по умолчанию для типа данных значений.  
  
 Если список параметров содержит необязательный параметр, каждый параметр, что следующий за ним также должен быть необязательным.  
  
 Модификатор `Optional` можно использовать в следующих контекстах:  
  
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  При вызове процедуры с или без необязательных параметров, можно передать аргументы по положению или по имени. Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Можно также определить с помощью перегрузка процедуры с необязательными параметрами. Если у вас есть один необязательный параметр, можно определить две перегруженные версии процедуры, принимающую параметр, а другой не. Дополнительные сведения см. в разделе [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
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
 Следующий пример демонстрирует вызов процедуры с аргументы, передаваемые по позиции и с аргументами, передаваемыми по имени. Процедура имеет два необязательных параметра.  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a>См. также

- [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
