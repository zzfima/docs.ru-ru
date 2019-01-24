---
title: Прочие типы данных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 7e32bf158b91c23c32028eb6877bd0089a9019b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655053"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Прочие типы данных (Visual Basic)
Visual Basic предоставляет несколько типов данных, не предназначенных для чисел или знаков. Вместо этого они работают с специализированном например Да/нет значений, значений даты и времени и адресов объектов.  
  
 Таблица, показывающая side-by-side сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Логический тип  
 [Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) является значением без знака, который интерпретируется как `True` или `False`. Ширина данных зависит от реализации платформы. Если переменная может содержать только два значения состояния, такие как true или false, Да/Нет, или Вкл/Выкл, объявите его как `Boolean`.  
  
## <a name="date-type"></a>Тип Date  
 [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) является 64-разрядное значение, которое содержит сведения о дате и времени. Каждое приращение представляет 100 наносекунд затраченного времени с начала (12:00 AM) 1 января 1 года по григорианскому календарю. Если переменная может содержать значение даты и значения времени, объявите его как `Date`.  
  
## <a name="object-type"></a>Тип объекта  
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32-разрядный адрес, который указывает на экземпляр объекта в приложении или в другом приложении. `Object` Переменные могут ссылаться на любой объект, ваше приложение распознавало или к данным любого типа данных. Это включает в себя *типы значений*, такие как `Integer`, `Boolean`, экземпляры структур и *ссылочные типы*, которые являются экземплярами объектов, созданных из классов, таких как `String`и <xref:System.Windows.Forms.Form>и экземпляры массивов.  
  
 Если переменная хранит указатель на экземпляр класса, который вы не знаете во время компиляции, или он может указывать на данные различных типов данных, он объявляется как `Object`.  
  
 Преимущество `Object` имеет тип данных, что его можно использовать для хранения данных любого типа данных. Недостатком является то, что с вас взиматься дополнительные операции, которые занимает больше времени выполнения и снижение производительности приложения. Если вы используете `Object` переменных для типов значений, то это вызовет *упаковки-преобразования* и *распаковки*. Если вы используете для ссылочных типов, то это вызовет *позднее связывание*.  
  
## <a name="see-also"></a>См. также
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
