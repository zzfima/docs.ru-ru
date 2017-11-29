---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a>Object Data Type
Содержит адреса, которые ссылаются на объекты. Можно назначить любой ссылочный тип (строка, массив, класс или интерфейс) `Object` переменной. `Object` Переменная также может ссылаться на данные любого типа значения (числовые, `Boolean`, `Char`, `Date`, структуры или перечисления).  
  
## <a name="remarks"></a>Примечания  
 `Object` Тип данных может указывать на данные любого типа данных, включая любое приложение распознает экземпляр объекта. Используйте `Object` при во время компиляции неизвестно, какой тип данных переменной может указывать на.  
  
 Значение по умолчанию `Object` — `Nothing` (ссылка null).  
  
## <a name="data-types"></a>Типы данных  
 Можно назначить переменную, константу или выражение любого типа данных для `Object` переменной. Определяет тип данных `Object` в настоящее время ссылается переменная, можно использовать <xref:System.Type.GetTypeCode%2A> метод <xref:System.Type?displayProperty=nameWithType> класса. Это показано в следующем примере.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 `Object` Тип данных является ссылочным типом. Однако Visual Basic обрабатывает `Object` переменной как тип значения, если она ссылается на данные типа значения.  
  
## <a name="storage"></a>Хранилище  
 Любой тип данных, которые он ссылается, `Object` сам, а — указатель на значение переменной не содержит значение данных. Она всегда занимает четыре байта в памяти компьютера, но это не относится к хранилища для данных, представляющих значение переменной. Поскольку код использует указатель для поиска данных `Object` переменной типа обрабатываются немного медленнее получить доступ к более явно типизированных переменных.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Вопросы взаимодействия.** Если выполняется взаимодействие с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, в других средах типы указателя несовместимы с Visual Basic `Object` типа.  
  
-   **Производительность.** Переменная объявляется с `Object` обладает достаточной гибкостью для содержат ссылку на объект любого типа. Тем не менее, при вызове метода или свойства для такой переменной всегда вызывается *позднего связывания* (во время выполнения). Чтобы принудительно *раннее связывание* (во время компиляции) и более высокую производительность, объявите переменную с определенное имя класса или привести его к определенному типу данных.  
  
     При объявлении переменной объекта, попробуйте использовать определенный тип класса, например <xref:System.OperatingSystem>, вместо обобщенный `Object` типа. Также следует использовать наиболее определенный класс доступен, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>таким образом, чтобы получить доступ к его свойствам и методам. Обычно можно использовать **классы** списка в **обозревателя объектов** для поиска имен доступных классов.  
  
-   **Расширяющие.** Все типы данных и все ссылочные типы расширяются до `Object` тип данных. Это означает, что любой тип можно преобразовать `Object` без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
     Тем не менее при преобразовании между типами значений и `Object`, Visual Basic выполняет операции *упаковка-преобразование* и *распаковки*, убедитесь в выполнении медленнее.  
  
-   **Символы типов.** `Object`не имеет знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** Соответствующий тип в .NET Framework — <xref:System.Object?displayProperty=nameWithType> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется `Object` переменную, указывающую на экземпляр объекта.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Практическое руководство. Определение идентичности двух объектов](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
