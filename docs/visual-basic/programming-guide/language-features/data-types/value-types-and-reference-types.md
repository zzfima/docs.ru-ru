---
title: Value Types and Reference Types
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cbab25e4af6b96ae22fe18d0b8a8fdbc7a7c7a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
В Visual Basic типы данных реализуются на основе их классификации. Типы данных Visual Basic могут классифицироваться в соответствии с переменной определенного типа, хранит ли собственные данные или указатель на данные. Если она хранит свои собственные данные *тип значения*; если он содержит указатель на данные в другом месте в памяти, это *ссылочному типу*.  
  
## <a name="value-types"></a>Типы значений  
 Тип данных является *тип значения* , если он содержит данные в пределах своей собственной памяти. Следующие типы значений:  
  
-   Все числовые типы данных  
  
-   `Boolean`, `Char` и `Date`  
  
-   Все структуры, даже если их члены являются ссылочными типами  
  
-   Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, или `ULong`  
  
 Каждая структура является типом значения, даже если он содержит члены ссылочного типа. По этой причине значение типы, такие как `Char` и `Integer` реализуются структуры .NET Framework.  
  
 Можно объявить тип значения с помощью зарезервированного ключевого слова, `Decimal`. Можно также использовать `New` ключевое слово для инициализации типа значений. Это особенно полезно в том случае, если тип имеет конструктор, который принимает параметры. Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новый `Decimal` значение из предоставленных частей.  
  
## <a name="reference-types"></a>Ссылочные типы  
 Объект *ссылочному типу* содержит указатель на другую область памяти, содержащую данные. Ссылочные типы включают следующие:  
  
-   `String`  
  
-   Все массивы, даже если их элементы являются типами значений  
  
-   Типы классов, таких как <xref:System.Windows.Forms.Form>  
  
-   Делегаты  
  
 Класс является *ссылочному типу*. По этой причине ссылочные типы, такие как `Object` и `String` поддерживаемых [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классы. Обратите внимание, что каждый массив является ссылочным типом, даже если его члены являются типами значений.  
  
 Поскольку каждый ссылочный тип представляет собой соответствующий класс .NET Framework, необходимо использовать [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово для его инициализации. Следующий оператор инициализирует массив.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Элементы, которые не являются типами  
 Следующие элементы программирования не квалифицируются как типы, так как нельзя указывать ни один из них как тип данных для объявленного элемента:  
  
-   Пространства имен  
  
-   Модули  
  
-   События  
  
-   Свойства и процедуры  
  
-   Переменные, константы и поля  
  
## <a name="working-with-the-object-data-type"></a>Работа с типом данных объекта  
 Можно назначить ссылочным типом или типом значения переменной `Object` тип данных. `Object` Переменная всегда содержит указатель на данные, а не сами данные. Однако если присвоить тип значения для `Object` переменной, он ведет себя как если бы она содержала свои собственные данные. Дополнительные сведения см. в разделе [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Можно выяснить, следует ли `Object` переменная используется в качестве ссылочным типом или типом значения, передайте ее в <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод в <xref:Microsoft.VisualBasic.Information> класс <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Возвращает `True` Если содержимое `Object` переменная представляет ссылочный тип.  
  
## <a name="see-also"></a>См. также  
 [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
