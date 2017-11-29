---
title: "Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4a682c7ae32ace0b1f859d52963342546a83f29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта
Объявите переменную [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) , указав `As Object` в [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Чтобы присвоить объект такой переменной, поместите его после знака равенства (`=`) в предложении назначения инструкции или инициализации.  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется `Object` переменной и назначает текущий экземпляр.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Объявление и присваивания можно объединять путем инициализации переменной в рамках его объявления. Следующий пример соответствует предыдущему примеру.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System>.  
  
-   Класс, структура или модуль, в котором для размещения `Dim` инструкции.  
  
-   Процедура, в которую будет помещен оператор присваивания.  
  
## <a name="see-also"></a>См. также  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
