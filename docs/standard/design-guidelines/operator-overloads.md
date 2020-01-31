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
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743684"
---
# <a name="operator-overloads"></a>Перегрузки операторов
Перегрузки операторов позволяют отображать типы платформ, как если бы они были встроенными примитивами языка.

 Хотя в некоторых ситуациях это разрешено и полезно, перегрузки операторов следует использовать осторожно. Существует множество случаев, когда перегрузка операторов была нарушена, например, когда конструкторы инфраструктуры начали использовать операторы для операций, которые должны быть простыми методами. Следующие рекомендации помогут решить, когда и как использовать перегрузку операторов.

 ❌ избежать определения перегрузок операторов, за исключением типов, которые должны иметь вид примитивов (встроенных) типов.

 ✔️ Рассмотрите возможность определения перегрузок операторов в типе, который должен иметь вид примитивного типа.

 Например, в <xref:System.String?displayProperty=nameWithType> определены `operator==` и `operator!=`.

 ✔️ определить перегрузки операторов в структурах, представляющих числа (например, <xref:System.Decimal?displayProperty=nameWithType>).

 ❌ не милые при определении перегрузок операторов.

 Перегрузка операторов полезна в случаях, когда она сразу же очевидна, как будет получен результат операции. Например, имеет смысл вычесть один <xref:System.DateTime> из другого `DateTime` и получить <xref:System.TimeSpan>. Однако не рекомендуется использовать оператор логического объединения для объединения двух запросов к базе данных или для записи в поток с помощью оператора сдвига.

 ❌ не предоставляют перегрузки операторов, если по крайней мере один из операндов не относится к типу, определяющему перегрузку.

 ✔️ операторы перегрузки в симметричном режиме.

 Например, если перегрузить `operator==`, необходимо также перегрузить `operator!=`. Аналогично, при перегрузке `operator<`также следует перегружать `operator>`и т. д.

 ✔️ Рассмотрите возможность предоставления методов с понятными именами, соответствующими каждому перегруженному оператору.

 Многие языки не поддерживают перегрузку операторов. По этой причине рекомендуется, чтобы типы, которые являются перегрузками операторов, включали дополнительный метод с соответствующим доменным именем, обеспечивающим эквивалентную функциональность.

 Следующая таблица содержит список операторов и соответствующие имена понятных методов.

|C#Символ оператора|Имя метаданных|Понятное имя|
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

### <a name="overloading-operator-"></a>Перегрузка оператора = =
 Перегрузка `operator ==` довольно сложная. Семантика оператора должна быть совместима с несколькими другими членами, например <xref:System.Object.Equals%2A?displayProperty=nameWithType>.

### <a name="conversion-operators"></a>Операторы преобразования
 Операторы преобразования — это унарные операторы, позволяющие выполнять преобразование из одного типа в другой. Операторы должны быть определены как статические члены либо в операнде, либо в типе возвращаемого значения. Существует два типа операторов преобразования: Implicit и EXPLICIT.

 ❌ не предоставлять оператор преобразования, если такое преобразование явно не ожидается конечными пользователями.

 ❌ не определяют операторы преобразования за пределами домена типа.

 Например, <xref:System.Int32>, <xref:System.Double>и <xref:System.Decimal> являются числовыми типами, а <xref:System.DateTime> — нет. Поэтому оператор преобразования для преобразования `Double(long)` в `DateTime`не предусмотрен. В этом случае предпочтительнее использовать конструктор.

 ❌ не предоставлять неявный оператор преобразования, если преобразование может быть невозможным.

 Например, не должно быть неявного преобразования из `Double` в `Int32`, так как `Double` имеет более широкий диапазон, чем `Int32`. Оператор явного преобразования может быть предоставлен даже в том случае, если преобразование потенциально теряется.

 ❌ не вызывайте исключения из неявных приведений.

 Конечным пользователям очень сложно понять, что происходит, так как они могут не знать, что выполняется преобразование.

 ✔️ выдавать <xref:System.InvalidCastException?displayProperty=nameWithType>, если вызов оператора CAST приводит к преобразованию потери данных и контракт оператора не допускает преобразования с потерей данных.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Правила разработки членов](../../../docs/standard/design-guidelines/member.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
