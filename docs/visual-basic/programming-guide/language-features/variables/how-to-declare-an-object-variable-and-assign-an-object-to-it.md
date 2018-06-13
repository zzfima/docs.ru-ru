---
title: Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648880"
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
