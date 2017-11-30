---
title: "Переменные структуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a>Переменные структуры (Visual Basic)
После создания структуры можно объявить переменные уровня модуля и процедуры для определенного типа. Например можно создать структуру, которая записывает сведения о системе компьютера. В следующем примере это показано.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Можно объявить переменные этого типа. Это показано в следующем объявлении.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  В классы и модули, структуры объявляются с помощью [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) по умолчанию для общего доступа. Если структура должна быть закрытой, убедитесь в том, объявите его с помощью [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово.  
  
## <a name="access-to-structure-values"></a>Доступ к значениям структуры  
 Для назначения и извлечения значений из переменных структуры элементов, используйте тот же синтаксис, как используются для задания и получения свойств объекта. Поместите оператор доступа к членам (`.`) между именем переменной структуры и имя элемента. Следующий пример получает доступ к элементам переменных, ранее объявленных как тип `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Присваивание переменных структуры  
 Также можно присвоить одну переменную в другой, если оба имеют одинаковый тип структуры. Соответствующие элементы в других это копирует все элементы из одной структуры. Это показано в следующем объявлении.  
  
```  
yourSystem = mySystem  
```  
  
 Если элемент структуры является ссылочным типом, например `String`, `Object`, или копируются в массив, указатель на данные. В предыдущем примере если `systemInfo` бы были включены переменной объекта, а затем копируется указатель из предыдущего примера `mySystem` для `yourSystem`, и изменение данных объекта через одну структуру будет действовать, если доступ осуществляется через другую структуру.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
