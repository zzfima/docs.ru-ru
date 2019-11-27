---
title: Прочие типы данных
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346334"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Прочие типы данных (Visual Basic)
Visual Basic предоставляет несколько типов данных, не ориентированных на числа или символы. Вместо этого они работают со специализированными данными, такими как значения Да/нет, значения даты и времени и адреса объектов.  
  
 Для таблицы, показывающей параллельное сравнение типов данных Visual Basic, см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Логический тип  
 [Логический тип данных](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) — это значение без знака, которое интерпретируется как `True` или `False`. Ширина данных зависит от платформы, реализующей реализацию. Если переменная может содержать только два значения, например true/false, да/нет или ON/OFF, объявите ее как `Boolean`.  
  
## <a name="date-type"></a>Тип даты  
 [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) — это 64-разрядное значение, содержащее сведения о дате и времени. Каждое приращение представляет 100 наносекунд времени, прошедшее с начала (12:00 AM) 1 января 1 года по григорианскому календарю. Если переменная может содержать значение даты, значение времени или и то, и другое, объявите ее как `Date`.  
  
## <a name="object-type"></a>Тип объекта  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) — это 32-разрядный адрес, указывающий на экземпляр объекта в приложении или в другом приложении. Переменная `Object` может ссылаться на любой объект, распознаваемый приложением, или на данные любого типа данных. К ним относятся оба *типа значений*, такие как `Integer`, `Boolean`и экземпляры структуры, а также *Ссылочные типы*, которые являются экземплярами объектов, созданных из таких классов, как `String` и <xref:System.Windows.Forms.Form>, и экземпляров массивов.  
  
 Если переменная хранит указатель на экземпляр класса, который не знает во время компиляции, или если он может указывать на данные различных типов данных, объявите его как `Object`.  
  
 Преимуществом `Object` типа данных является то, что его можно использовать для хранения данных любого типа данных. Недостаток заключается в том, что вы получаете дополнительные операции, которые требуют больше времени на выполнение и делают приложение более медленным. При использовании переменной `Object` для типов значений необходимо выполнить *упаковку* и распаковку. При использовании его для ссылочных типов требуется *позднее связывание*.  
  
## <a name="see-also"></a>См. также

- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
