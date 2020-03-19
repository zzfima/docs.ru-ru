---
title: Перегрузки операторов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401223"
---
# <a name="operator-overloads"></a>Перегрузки операторов
Перегрузки оператора позволяют типам фреймворков отображаться так, как если бы они были встроенными примитивами языка.

 Хотя это допустимо и полезно в некоторых ситуациях, оператор перегрузки должны использоваться осторожно. Есть много случаев, когда перегрузка оператора была злоупотреблять, например, когда конструкторы фреймворков начали использовать операторов для операций, которые должны быть простыми методами. Следующие рекомендации должны помочь вам решить, когда и как использовать перегрузку оператора.

 ❌AVOID определяет перегрузки оператора, за исключением типов, которые должны чувствовать себя примитивными (встроенными) типами.

 ✔️ CONSIDER, определяющий перегрузки оператора в типе, который должен чувствовать себя примитивным типом.

 Например, <xref:System.String?displayProperty=nameWithType> `operator==` имеет `operator!=` и определяется.

 ✔️ DO определяют перегрузки оператора в структурках, представляющих числа <xref:System.Decimal?displayProperty=nameWithType>(например,).

 ❌НЕ быть милопри определяя перегрузки оператора.

 Перегрузка оператора полезна в тех случаях, когда сразу становится ясно, каким будет результат операции. Например, имеет смысл, чтобы иметь <xref:System.DateTime> возможность `DateTime` вычесть <xref:System.TimeSpan>один из другого и получить . Однако нецелесообразно использовать оператора логического союза для объединения двух запросов базы данных или для записи оператора смены в поток.

 ❌НЕ предоставляйте оператору перегрузки, если по крайней мере один из operands не имеет типа, определяющего перегрузку.

 ✔️ перегрузки операторов симметричным образом.

 Например, если вы `operator==`перегружаете, `operator!=`вы также должны перегрузить . Аналогичным образом, если `operator<`вы перегружаете `operator>`, вы также должны перегрузить , и так далее.

 ✔️ CONSIDER предоставляет методы с дружественными именами, которые соответствуют каждому перегруженного оператора.

 Многие языки не поддерживают перегрузку оператора. По этой причине рекомендуется, чтобы типы, перегружающие операторов, включали вторичный метод с соответствующим доменным именем, обеспечивающим эквивалентную функциональность.

 Следующая таблица содержит список операторов и соответствующие имена дружественных методов.

|Символ оператора СЗ|Имя метаданных|Понятное имя|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a>Оператор перегрузки
 Перегрузка `operator ==` довольно сложна. Семантика оператора должна быть совместима с несколькими <xref:System.Object.Equals%2A?displayProperty=nameWithType>другими участниками, такими как .

### <a name="conversion-operators"></a>Операторы преобразования
 Операторы конверсии являются неопроизвонелыми операторами, которые позволяют конверсировать из одного типа в другой. Операторы должны быть определены как статические члены либо на операнде, либо на типе возврата. Существует два типа операторов конверсий: неявный и явный.

 ❌НЕ предоставляйте оператора конверсии, если такое преобразование явно не ожидается конечными пользователями.

 ❌НЕ определяйте операторов конверсии за пределами домена типа.

 Например, <xref:System.Int32> <xref:System.Double>, <xref:System.Decimal> и все численные типы, в то время как <xref:System.DateTime> нет. Таким образом, не должно быть `Double(long)` оператора `DateTime`преобразования для преобразования в . В таком случае предпочтительнее конструктор.

 ❌НЕ предоставляйте оператора неявного преобразования, если преобразование потенциально убыточно.

 Например, не должно быть неявного преобразования от `Double` к потому, `Int32` что `Double` имеет более широкий диапазон, чем `Int32`. Оператор явного преобразования может быть предоставлен, даже если конверсия потенциально убыточна.

 ❌НЕ выбрасывайте исключения из неявных слепков.

 Конечным пользователям очень трудно понять, что происходит, потому что они могут не знать, что происходит преобразование.

 ✔️ DO <xref:System.InvalidCastException?displayProperty=nameWithType> throw, если вызов литой оператора приводит к убыточной конверсии и договор оператора не позволяет убыточные преобразования.

 *Порции © 2005, 2009 Microsoft Corporation. Все права зарезервированы.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также раздел

- [Правила разработки членов](../../../docs/standard/design-guidelines/member.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
