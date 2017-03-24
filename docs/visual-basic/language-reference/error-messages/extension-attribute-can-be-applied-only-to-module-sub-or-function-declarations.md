---
title: "Атрибут «Расширения» может применяться только к объявлениям «Модуль», «Sub» или «Функция» | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3eee008f737bf625023b6e4d58e1df7d282148d3
ms.lasthandoff: 03/13/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>Атрибут «Расширения» может применяться только к объявлениям «Модуль», «Sub» или «Функция»
Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедуры или `Function` процедуры. Все методы расширения должен быть помечен атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=fullName>имен.</xref:System.Runtime.CompilerServices?displayProperty=fullName> Кроме того модуль, содержащий метод расширения может быть помечен таким же образом. Не используется атрибут расширения является допустимым.  
  
 **Идентификатор ошибки:** BC36550  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите атрибут расширения.  
  
-   Измените расширение в качестве метода, определенного в вложенного модуля.  
  
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
 [Общие сведения об атрибутах](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
