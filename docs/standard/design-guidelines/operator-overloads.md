---
title: Перегрузки операторов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 747fc21aceae60e362c72391ae265e45d6f8445f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579318"
---
# <a name="operator-overloads"></a>Перегрузки операторов
Перегрузки операторов разрешить отображаются, как если бы они были примитивы языка встроенных типов framework.  
  
 Несмотря на то, что разрешенные, так и в определенных ситуациях, перегрузки операторов следует использовать осторожно. Существует много случаев, в какой оператор перегрузка были злоупотреблениям в виде, например при запуске конструкторы framework использование операторов для операций, которые должны быть простые методы. Следующие рекомендации помогут вам решить, когда и как использовать перегрузку операторов.  
  
 **X ИЗБЕГАЙТЕ** определения перегрузки оператора, за исключением того, в типах, которые следует воспринимается как типы-примитивы (встроенные).  
  
 **✓ Попробуйте** определения перегрузки оператора в типе, который следует кажется типом-примитивом.  
  
 Например <xref:System.String?displayProperty=nameWithType> имеет `operator==` и `operator!=` определен.  
  
 **СДЕЛАТЬ ✓** определения перегрузки операторов в структур, которые представляют собой числа (например, <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X не** быть забавны при определении перегрузки операторов.  
  
 Перегрузка операторов полезно в случаях, когда очевиден результат операции, которые будут. Например, имеет смысл получить возможность вычесть единицу <xref:System.DateTime> из другого `DateTime` и получить <xref:System.TimeSpan>. Тем не менее он не подходит для использования логического оператора union объединения двух запросов к базе данных или использовать оператор сдвига для записи в поток.  
  
 **X не** предоставляют перегрузки оператор, если по крайней мере один из операндов имеет тип, определив перегрузку.  
  
 **✓ СДЕЛАТЬ** перегружать операторы симметричную.  
  
 Например, при перегрузке `operator==`, следует также перегрузить `operator!=`. Аналогично при перегрузке `operator<`, следует также перегрузить `operator>`, и т. д.  
  
 **✓ Попробуйте** предоставлять методы с понятными именами, которые соответствуют каждой перегруженный оператор.  
  
 Многие языки не поддерживают перегрузку операторов. По этой причине рекомендуется Включение дополнительный метод с соответствующим именем конкретного домена, обеспечивающее эквивалентную функциональность типов, перегрузку операторов.  
  
 Следующая таблица содержит список операторов и имена соответствующих понятное методов.  
  
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
 Перегрузка `operator ==` — довольно сложными. Семантика оператора требуется для обеспечения совместимости с несколько других элементов, таких как <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Операторы преобразования  
 Операторы преобразования являются унарные операторы, позволяющие преобразование из одного типа в другой. Операторы должны быть определены как статические члены на операнд или тип возвращаемого значения. Существует два типа операторов преобразования: явные и неявные.  
  
 **X не** предоставить оператор преобразования, если такое преобразование не ожидается конечными пользователями.  
  
 **X не** определить операторы преобразования за пределами области типа.  
  
 Например <xref:System.Int32>, <xref:System.Double>, и <xref:System.Decimal> являются все числовые типы, в то время как <xref:System.DateTime> не является. Таким образом, должно быть не оператор преобразования `Double(long)` для `DateTime`. В этом случае является предпочтительным конструктор.  
  
 **X не** предоставить неявный оператор преобразования, если преобразование является потенциально с потерями.  
  
 Например, не должно быть неявное преобразование из `Double` для `Int32` из-за `Double` имеет широкий диапазон, чем `Int32`. Оператор явного преобразования может быть указано, даже если преобразование является потенциально с потерями.  
  
 **X не** вызывайте исключения из неявных приведений типов.  
  
 Это очень сложно конечным пользователям понять, что произошло, потому что не будут знать, что происходит преобразования.  
  
 **СДЕЛАТЬ ✓** throw <xref:System.InvalidCastException?displayProperty=nameWithType> случае вызов оператора приведения преобразование с потерями и контракт оператора не допускает преобразования с потерей данных.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Правила разработки членов](../../../docs/standard/design-guidelines/member.md)  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
