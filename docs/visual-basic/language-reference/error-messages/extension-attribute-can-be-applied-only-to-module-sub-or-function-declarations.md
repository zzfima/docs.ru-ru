---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 88212fb2c04eab61b719a161ae01ccdda9a6110d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640723"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедуры или `Function` процедуры. Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен. Кроме того модуль, содержащий метод расширения может быть помечен таким же образом. Не используется атрибут расширения является допустимым.  
  
 **Идентификатор ошибки:** BC36550  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите атрибут расширения.  
  
- Измените расширение в качестве метода, определенного в заключающего модуля.  
  
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
