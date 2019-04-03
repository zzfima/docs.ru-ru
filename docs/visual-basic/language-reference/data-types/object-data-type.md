---
title: Тип данных объекта (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 616110145db2796e05509094b1c023daacd68f03
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835574"
---
# <a name="object-data-type"></a>Object Data Type
Содержит адреса, которые ссылаются на объекты. Можно назначить любой ссылочный тип (строка, массив, класс или интерфейс) `Object` переменной. `Object` Переменная также может ссылаться на данные любого типа значения (числовые, `Boolean`, `Char`, `Date`, структуры или перечисления).  
  
## <a name="remarks"></a>Примечания  
 `Object` Тип данных может указывать на данные любого типа данных, включая любой экземпляр объекта, ваше приложение распознавало. Используйте `Object` при во время компиляции неизвестно, какой тип данных переменной может указывать на.  
  
 Значение по умолчанию `Object` является `Nothing` (ссылкой на null).  
  
## <a name="data-types"></a>Типы данных  
 Можно назначить переменную, константу или выражение любого типа данных для `Object` переменной. Чтобы определить тип данных `Object` в настоящее время ссылается переменная, можно использовать <xref:System.Type.GetTypeCode%2A> метод <xref:System.Type?displayProperty=nameWithType> класса. Это показано в следующем примере.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 `Object` Тип данных является ссылочным типом. Тем не менее, Visual Basic обрабатывает `Object` переменной как тип значения, если она ссылается на данные типа значения.  
  
## <a name="storage"></a>Хранилище  
 Любой тип данных, которые он ссылается, `Object` отдельно, однако вместо указатель на значение переменной не содержит значения данных. В ней всегда используется четыре байта в памяти компьютера, но это не относится к хранилище для данных, представляющих значение переменной. Поскольку код использует указатель для поиска данных `Object` переменных типа обрабатываются немного медленнее, для доступа по сравнению с явно типизированные переменные.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, не забывайте, что в других средах типы указателей не совместимы с Visual Basic `Object` типа.  
  
-   **Производительность.** Переменная, объявляемая с `Object` тип является достаточно гибким, чтобы содержать ссылку на любой объект. Тем не менее, при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения). Чтобы принудительно *раннее связывание* (во время компиляции) и более высокую производительность, объявите переменную с определенное имя класса или привести к типу данных.  
  
     При объявлении переменной объекта, попробуйте использовать определенный тип класса, например <xref:System.OperatingSystem>, вместо универсального `Object` типа. Также следует использовать наиболее конкретный класс доступен, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>, позволяя получать доступ к его свойствам и методам. Обычно можно использовать **классы** в списке **обозреватель объектов** для поиска имен доступных классов.  
  
-   **Расширяющие.** Все типы данных и все ссылочные типы расширяющего преобразования к `Object` тип данных. Это означает, что любой тип можно преобразовать `Object` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
     Тем не менее при преобразовании между типами значений и `Object`, Visual Basic выполняет операции *упаковки-преобразования* и *распаковки*, поэтому оказаться, что замедляет выполнение.  
  
-   **Символы типа.** `Object` не имеет знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** Соответствующий тип в .NET Framework — <xref:System.Object?displayProperty=nameWithType> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано `Object` переменной, указывающей на экземпляр объекта.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Практическое руководство. Определение связи между двумя объектами](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
