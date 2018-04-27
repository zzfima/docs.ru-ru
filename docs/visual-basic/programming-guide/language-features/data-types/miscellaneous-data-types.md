---
title: Прочие типы данных (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a>Прочие типы данных (Visual Basic)
Visual Basic предоставляет несколько типов данных, не предназначенных для чисел или символов. Они предусмотрены для настраиваемых данных, таких как Да/нет значений, значений даты и времени и адресов объектов.  
  
 Таблица, показывающая сравнение типы данных Visual Basic, см. [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Логический тип  
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) имеет значение без знака, которое интерпретируется как `True` или `False`. Ширина данных зависит от реализации платформы. Если переменная может содержать только два значения состояния, например true или false, Да/Нет или Вкл/Выкл, объявите его как `Boolean`.  
  
## <a name="date-type"></a>Date-тип  
 [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) — 64-разрядное значение, которое содержит сведения о дате и времени. Каждое приращение представляет 100 наносекунд затраченного времени с начала (12:00 AM) 1 января 1 года по григорианскому календарю. Если переменная может содержать значение даты и времени значение, он объявляется как `Date`.  
  
## <a name="object-type"></a>Тип объекта  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32-разрядный адрес, который указывает на экземпляр объекта в приложении или в другом приложении. `Object` Переменной может указывать на любой объект, распознаваемый приложением, а также данные любого типа данных. Это включает в себя *типы значений*, такие как `Integer`, `Boolean`, экземпляры структур и *ссылочные типы*, которые являются экземплярами объектов, созданных из классов, таких как `String`и <xref:System.Windows.Forms.Form>и экземпляры массивов.  
  
 Если переменная хранит указатель на экземпляр класса, который вы не знаете во время компиляции, или он может указывать на данные различных типов данных, он объявляется как `Object`.  
  
 Преимущество `Object` имеет тип данных, его можно использовать для хранения данных любого типа данных. Недостаток заключается в том, что при этом дополнительные операции, занимает больше времени выполнения и снижение производительности приложения. Если вы используете `Object` переменных для типов значений, при этом *упаковка-преобразование* и *распаковки*. Если вы используете для ссылочных типов, при этом *позднего связывания*.  
  
## <a name="see-also"></a>См. также  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
