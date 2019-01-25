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
author: KrzysztofCwalina
ms.openlocfilehash: 441dc2777cd8d221300c526b6b31a647af60ca71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646582"
---
# <a name="operator-overloads"></a>Перегрузки операторов
Перегрузки операторов позволяют типы framework отображаться так, как если бы они были примитивы встроенный язык.  
  
 Несмотря на то, что разрешенных и полезен в некоторых ситуациях, перегрузки операторов следует использовать осторожно. Есть много таких ситуаций, в которых оператор перегрузка были злонамеренное использование, например при запуске конструкторах framework использование операторов для операций, которые должны быть простые методы. Следующие рекомендации помогут вам решить, когда и как использовать перегрузку операторов.  
  
 **X AVOID** определения перегрузки оператора, за исключением того, в типах, которые следует воспринимается как типы-примитивы (встроенные).  
  
 **✓ CONSIDER** определения перегрузки оператора в типе, который следует кажется типом-примитивом.  
  
 Например <xref:System.String?displayProperty=nameWithType> имеет `operator==` и `operator!=` определен.  
  
 **✓ DO** определения перегрузки операторов в структур, которые представляют собой числа (например, <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** быть забавны при определении перегрузки операторов.  
  
 Перегрузка операторов полезно в случаях, в которых совершенно очевидно, каким будет результат операции. Например, имеет смысл иметь возможность вычесть единицу <xref:System.DateTime> из другого `DateTime` и получите <xref:System.TimeSpan>. Тем не менее он не подходит для использования оператора логического объединения объединения двух запросов к базе данных, или оператор сдвига для записи в поток.  
  
 **X DO NOT** предоставляют перегрузки оператор, если по крайней мере один из операндов имеет тип, определив перегрузку.  
  
 **✓ DO** перегружать операторы симметричную.  
  
 Например, при перегрузке `operator==`, следует также перегрузить `operator!=`. Аналогично при перегрузке `operator<`, следует также перегрузить `operator>`, и т. д.  
  
 **✓ CONSIDER** предоставлять методы с понятными именами, которые соответствуют каждой перегруженный оператор.  
  
 Многие языки не поддерживают перегрузку операторов. По этой причине рекомендуется Включение дополнительного метода с соответствующим именем домена, обеспечивающее эквивалентную функциональность типы с перегруженными операторами.  
  
 Следующая таблица содержит список операторов и имена соответствующих методов понятное.  
  
|Символ оператора C#|Имя метаданных|Понятное имя|  
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
  
### <a name="overloading-operator-"></a>Перегрузка оператора ==  
 Перегрузка `operator ==` довольно сложен. Семантика оператора должны быть совместим с несколько других элементов, таких как <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Операторы преобразования  
 Операторы преобразования являются унарными операторами, которые позволяют преобразовывать из одного типа в другой. Операторы должны определяться как статические члены на операнд или тип возвращаемого значения. Существует два типа операторов преобразования: явные и неявные.  
  
 **X DO NOT** предоставить оператор преобразования, если такое преобразование не ожидается конечными пользователями.  
  
 **X DO NOT** определить операторы преобразования за пределами области типа.  
  
 Например <xref:System.Int32>, <xref:System.Double>, и <xref:System.Decimal> являются все числовые типы, тогда как <xref:System.DateTime> не является. Таким образом, должно быть не оператор преобразования `Double(long)` для `DateTime`. В этом случае рекомендуется использовать конструктор.  
  
 **X DO NOT** предоставить неявный оператор преобразования, если преобразование является потенциально с потерями.  
  
 Например, не должно быть неявное преобразование из `Double` для `Int32` поскольку `Double` имеет широкий диапазон, чем `Int32`. Могут быть предоставлены явный оператор преобразования, даже если преобразование является потенциально с потерями.  
  
 **X DO NOT** вызывайте исключения из неявных приведений типов.  
  
 Очень трудно для конечных пользователей понять, что происходит, так как они могут быть виду, что преобразование выполняется.  
  
 **✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> случае вызов оператора приведения преобразование с потерями и контракт оператора не допускает преобразования с потерей данных.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Правила разработки членов](../../../docs/standard/design-guidelines/member.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
