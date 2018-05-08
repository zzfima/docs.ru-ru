---
title: Значение типа &#39;тип1&#39; не может быть преобразован &#39;тип2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>Значение типа &#39;тип1&#39; не может быть преобразован &#39;тип2&#39;
Не удается преобразовать значение типа «тип1» в «тип2». Свойство «Значение» для получения строкового значения первого элемента "\<Родительскийэлемент >".  
  
 Предпринята попытка неявного приведения XML-литерала к определенному типу. XML-литерал не может быть неявно приведен к указанному типу.  
  
 **Идентификатор ошибки:** BC31194  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`. Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Convert>  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
