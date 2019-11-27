---
title: Оператор Yield
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 72a8dafdc5aa834a644e1e70a309cfc0827b5fdf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352722"
---
# <a name="yield-statement-visual-basic"></a>Оператор Yield (Visual Basic)
Отправляет следующий элемент коллекции в оператор `For Each...Next`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Параметры  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательно. Выражение, которое неявно преобразуется в тип функции итератора или `Get` метода доступа, содержащего инструкцию `Yield`.|  
  
## <a name="remarks"></a>Примечания  
 Оператор `Yield` возвращает по одному элементу коллекции за раз. Оператор `Yield` входит в функцию итератора или метод доступа `Get`, который выполняет пользовательские итерации по коллекции.  
  
 Для использования функции итератора используется оператор [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или запрос LINQ. Каждая итерация цикла `For Each` вызывает функцию итератора. При достижении оператора `Yield` в функции итератора возвращается `expression`, а текущее расположение в коде сохраняется. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Неявное преобразование должно существовать из типа `expression` в операторе `Yield` в тип возвращаемого значения итератора.  
  
 Для завершения итерации можно использовать инструкцию `Exit Function` или `Return`.  
  
 "Yield" не является зарезервированным словом и имеет специальное значение только в том случае, если оно используется в функции `Iterator` или методе доступа `Get`.  
  
 Дополнительные сведения о функциях итераторов и `Get` методов доступа см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Функции итераторов и методы доступа Get  
 Объявление функции итератора или метода доступа `Get` должно соответствовать следующим требованиям.  
  
- Он должен включать модификатор [итератора](../../../visual-basic/language-reference/modifiers/iterator.md) .  
  
- Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
- У него не может быть `ByRef` параметров.  
  
 Функция итератора не может присутствовать в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Функция итератора может быть анонимной функцией. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Обработка исключений  
 Оператор `Yield` может находиться в блоке `Try` блока [try... Перехватить... Оператор finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Блок `Try`, содержащий инструкцию `Yield`, может иметь `Catch` блоки и может иметь блок `Finally`.  
  
 Оператор `Yield` не может находиться в блоке `Catch` или в блоке `Finally`.  
  
 Если тело `For Each` (за пределами функции итератора) создает исключение, блок `Catch` в функции-итераторе не выполняется, но выполняется блок `Finally` в функции итератора. Блок `Catch` внутри функции итератора перехватывает только исключения, происходящие внутри функции итератора.  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Следующий код возвращает `IEnumerable (Of String)` из функции итератора, а затем проходит по элементам `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Вызов `MyIteratorFunction` не выполняет тело функции. Вместо этого вызов возвращает `IEnumerable(Of String)` в переменную `elements`.  
  
 В итерации цикла `For Each` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`. Этот вызов выполняет тело `MyIteratorFunction` до достижения следующего оператора `Yield`. Оператор `Yield` Возвращает выражение, которое определяет не только значение переменной `element` для использования в теле цикла, но также свойство <xref:System.Collections.Generic.IEnumerator%601.Current%2A> элементов, которое является `IEnumerable (Of String)`.  
  
 В каждой последующей итерации цикла `For Each` выполнение тела итератора продолжается с места остановки и при достижении оператора `Yield` оно снова останавливается. Цикл `For Each` завершается при достижении конца функции итератора или оператора `Return` или `Exit Function`.  
  
## <a name="example"></a>Пример  
 В следующем примере имеется оператор `Yield`, который находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл. Каждая итерация тела оператора [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в `Main` создает вызов функции итератора `Power`. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 Тип возвращаемого значения метода итератора — <xref:System.Collections.Generic.IEnumerable%601>, тип интерфейса итератора. При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. Объявление свойства содержит модификатор `Iterator`.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также

- [Операторы](../../../visual-basic/language-reference/statements/index.md)
