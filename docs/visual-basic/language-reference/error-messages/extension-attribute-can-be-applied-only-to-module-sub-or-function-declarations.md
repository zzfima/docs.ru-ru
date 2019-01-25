---
title: '&#39;Расширение&#39; атрибут может применяться только к &#39;модуль&#39;, &#39;Sub&#39;, или &#39;функция&#39; объявления'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: fabd602f31a362fe33954253d565e86a065e0a83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718238"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;Расширение&#39; атрибут может применяться только к &#39;модуль&#39;, &#39;Sub&#39;, или &#39;функция&#39; объявления
Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедуры или `Function` процедуры. Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен. Кроме того модуль, содержащий метод расширения может быть помечен таким же образом. Не используется атрибут расширения является допустимым.  
  
 **Идентификатор ошибки:** BC36550  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите атрибут расширения.  
  
-   Измените расширение в качестве метода, определенного в заключающего модуля.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Print` метод `String` тип данных.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a>См. также
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
