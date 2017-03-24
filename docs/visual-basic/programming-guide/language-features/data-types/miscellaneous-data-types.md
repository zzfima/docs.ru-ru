---
title: "Прочие типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2de377fa9dfd7ec13cdbb9b700f8485b0c0e2106
ms.lasthandoff: 03/13/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a>Прочие типы данных (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]имеется несколько типов данных, не предназначенных для чисел или знаков. Они предусмотрены для настраиваемых данных, таких как логический значений, значений даты и времени и адресов объектов.  
  
 Для таблицы, сравнение side-by-side [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] типы данных в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Логический тип  
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение без знака, интерпретируется как `True` или `False`. Ширина данных зависит от реализации платформы. Если переменная может содержать только два значения состояния, такие как ИСТИНА или ЛОЖЬ, Да или нет, или Вкл/Выкл, он объявляется как `Boolean`.  
  
## <a name="date-type"></a>Date-тип  
 [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) — 64-разрядное значение, которое содержит сведения о дате и времени. Каждое приращение представляет 100 наносекунд времени с начала (12:00 AM) 1 января 1 года по григорианскому календарю. Если переменная может содержать значение даты и значения времени, он объявляется как `Date`.  
  
## <a name="object-type"></a>Тип объекта  
 [Тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32-разрядный адрес, который указывает на экземпляр объекта в приложении или в другом приложении. `Object` Переменная может ссылаться на любой объект, распознаваемый приложением, или данные любого типа данных. Это включает в себя *типы значений*, такие как `Integer`, `Boolean`, экземпляры структур и *ссылочные типы*, которые являются экземплярами объектов, созданных из классов, таких как `String` и <xref:System.Windows.Forms.Form>и экземпляры массивов.</xref:System.Windows.Forms.Form>  
  
 Если переменная хранит указатель на экземпляр класса, который во время компиляции неизвестно, или он может указывать на данные различных типов данных, он объявляется как `Object`.  
  
 Преимущество `Object` имеет тип данных, можно использовать его для хранения данных любого типа данных. Недостатком являются дополнительные операции, которые занимает больше времени выполнения и снижение производительности приложения. При использовании `Object` переменных для типов значений, то это вызовет *упаковки* и *распаковки*. Если она используется для ссылочных типов, вызывается *позднего связывания*.  
  
## <a name="see-also"></a>См. также  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
