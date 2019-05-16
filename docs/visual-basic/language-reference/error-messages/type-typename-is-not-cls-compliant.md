---
title: Тип <typename> несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 2805cac71cb36d21f5ab21a5875183803d07a4b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642369"
---
# <a name="type-typename-is-not-cls-compliant"></a>Тип \<typename > не является CLS-совместимым
Переменная, свойство или возвращаемое значение функции объявлен с типом данных, не является CLS-совместимым.  
  
 Для приложения на соответствие стандарту [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он должен использовать только типы, совместимые с CLS.  
  
 Следующие типы данных Visual Basic не являются CLS-совместимыми:  
  
- [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Идентификатор ошибки:** BC40041  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если приложение должно быть CLS-совместимыми, измените тип данных этого элемента на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
- Если приложения не должны быть CLS-совместимым, ничего менять не нужно. Вы должны помнить его несоответствия, однако.
