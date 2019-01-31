---
title: 'Невозможно преобразовать значение типа  в '
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: eb30d63e83452e75f353c44a9d0445c7dbb1013a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287512"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Невозможно преобразовать значение типа  в 
Значение типа «тип1» не может быть преобразован в «тип2». Можно использовать свойство «Value», чтобы получить строковое значение первого элемента "\<Родительскийэлемент >".  
  
 Предпринята попытка неявного приведения XML-литерала к определенному типу. XML-литерал не может быть неявно приведен к указанному типу.  
  
 **Идентификатор ошибки:** BC31194  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`. Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.  
  
## <a name="see-also"></a>См. также
- <xref:System.Convert>
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
