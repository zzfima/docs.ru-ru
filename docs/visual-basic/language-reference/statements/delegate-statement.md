---
title: "Оператор Delegate | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 9ac9e28c82f8a6b5a9c1398961d831c956a649e0
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-statement"></a>Оператор Delegate
Используется для объявления делегата. Делегат — это ссылочный тип, который ссылается на `Shared` метод типа или на метод экземпляра объекта. Для создания экземпляра класса данного делегата может использоваться любая процедура с соответствующими типами параметров и возвращаемых. Процедура может затем быть вызвана через экземпляр делегата.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attrlist`|Необязательный. Список атрибутов, которые применяются для данного делегата. Несколько атрибутов разделяются запятыми. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).|  
|`accessmodifier`|Необязательный. Указывает, какой код может обращаться к делегату. Ниже указаны доступные значения.<br /><br /> -   [Открытые](../../../visual-basic/language-reference/modifiers/public.md). Любой код, который можно получить доступ к элементу, который объявляет делегат может прочитать его.<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md). Только код в пределах класса делегата или производного класса можно получить доступ к его.<br />-   [Дружественные](../../../visual-basic/language-reference/modifiers/friend.md). Только код внутри одной сборки можно получить доступ к делегата.<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md). Только код внутри элемента, который объявляет делегат может прочитать его.<br /><br /> Можно указать `Protected Friend` для обеспечения доступа из кода внутри класса делегата, производного класса или той же сборки.|  
|`Shadows`|Необязательный. Указывает, что данный делегат повторно объявляет и скрывает идентично именованный программный элемент или набор перегружаемых элементов в базовом классе. Можно скрыть любой тип объявленного элемента, используя любой другой тип.<br /><br /> Скрытый элемент недоступен из производного класса, который его скрывает, за исключением тех классов, из которых недоступен скрывающий элемент. Например если `Private` элемент затеняет элемент базового класса, код, который не имеет разрешения на доступ к `Private` элемент обращается к элементу базового класса.|  
|`Sub`|Необязательно, но либо `Sub` или `Function` должно отображаться. Объявляет процедуру как делегат `Sub` процедуру, которая не возвращает значение.|  
|`Function`|Необязательно, но либо `Sub` или `Function` должно отображаться. Объявляет процедуру как делегат `Function` процедуры, возвращающей значение.|  
|`name`|Обязательный. Имя типа делегата. следует стандартным правилам именования переменных.|  
|`typeparamlist`|Необязательный. Список параметров типа для этого делегата. Несколько параметров типа разделяются запятыми. Кроме того, каждый параметр типа можно объявить как вариант с использованием `In` и `Out` универсальных модификаторов. Необходимо заключить [список типов](../../../visual-basic/language-reference/statements/type-list.md) в круглые скобки и ввести его с `Of` ключевое слово.|  
|`parameterlist`|Необязательный. Список параметров, передаваемых в процедуру при ее вызове. Необходимо заключить [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) в круглые скобки.|  
|`type`|Требуется, если указана `Function` процедуры. Тип данных возвращаемого значения.|  
  
## <a name="remarks"></a>Примечания  
 `Delegate` Оператор определяет типы параметров и возвращаемых классом делегата. Для создания экземпляра класса данного делегата может использоваться любая процедура с соответствующими параметрами и возвращаемыми типами. Процедура может затем быть вызвана через экземпляр делегата путем вызова делегата `Invoke` метод.  
  
 Делегаты можно объявлять на пространства имен, модуля, класса или структуры, но не внутри процедуры.  
  
 Каждый класс делегата определяет конструктор, которому передается спецификация метода объекта. Аргумент конструктора делегата должен быть ссылкой на метод или лямбда-выражение.  
  
 Чтобы указать ссылку на метод, используйте следующий синтаксис:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Тип во время компиляции `expression` должно быть именем класса или интерфейса, который содержит метод с указанным именем, сигнатура которого соответствует сигнатуре класса делегата. `methodname` Может быть совместно используемым методом или методом экземпляра. `methodname` Не является обязательным, даже если создается делегат для метода по умолчанию для класса.  
  
 Чтобы указать лямбда-выражение, используйте следующий синтаксис:  
  
 `Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`  
  
 Подпись функции должна соответствовать типу делегата. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Дополнительные сведения о делегатах см. в разделе [делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Delegate` инструкцию, чтобы объявить делегат для работы с двумя числами и возвращает число. `DelegateTest` Метод принимает экземпляр делегата этого типа и использует его для работы с парой чисел.  
  
 [!code-vb[VbVbalrDelegates&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Предложение Of (Visual Basic)](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Практическое руководство: использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Ковариация и контрвариация](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8)   
 [В](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Выход](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
