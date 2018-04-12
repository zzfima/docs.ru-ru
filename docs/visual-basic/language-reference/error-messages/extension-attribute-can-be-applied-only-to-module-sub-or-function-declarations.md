---
title: '&#39; Расширение &#39; атрибут может применяться только к &#39; Модуль &#39; &#39; По &#39; или &#39; Функция &#39; объявления'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39; Расширение &#39; атрибут может применяться только к &#39; Модуль &#39; &#39; По &#39; или &#39; Функция &#39; объявления
Единственный способ расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Методом расширения могут быть `Sub` процедуры или `Function` процедуры. Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>`, из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен. При необходимости модуль, который содержит метод расширения может быть помечен таким же образом. Не используется расширение атрибута является допустимым.  
  
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
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
