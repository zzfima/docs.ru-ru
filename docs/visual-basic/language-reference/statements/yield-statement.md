---
title: Оператор Yield (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: e417e13f1617f3ad8064c9e1b0eec835938b6200
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978925"
---
# <a name="yield-statement-visual-basic"></a>Оператор Yield (Visual Basic)
Отправляет следующий элемент коллекции `For Each...Next` инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, которое может быть неявно преобразован в тип функции итератора или `Get` метод доступа, который содержит `Yield` инструкции.|  
  
## <a name="remarks"></a>Примечания  
 `Yield` Инструкция возвращает один элемент из коллекции за раз. `Yield` Включаются инструкции в функции итератора или `Get` доступа, который выполнять пользовательские итерации по коллекции.  
  
 Использование функции итератора с помощью [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или запрос LINQ. Каждая итерация `For Each` цикл вызывает функции итератора. Когда `Yield` достижения оператора в функции итератора, `expression` возвращается, при этом сохраняется текущее расположение в коде. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Должно существовать неявное преобразование из типа `expression` в `Yield` инструкцию, чтобы тип возвращаемого значения итератора.  
  
 Можно использовать `Exit Function` или `Return` инструкции для завершения итерации.  
  
 «Yield» не является зарезервированным словом и имеет специальное значение только в том случае, если он используется в `Iterator` функции или `Get` метода доступа.  
  
 Дополнительные сведения о функции итераторов и `Get` методы доступа, см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Функции итератора и методы доступа Get  
 Объявление функции итератора или `Get` метод доступа должен соответствовать следующим требованиям:  
  
-   Она должна включать [итератор](../../../visual-basic/language-reference/modifiers/iterator.md) модификатор.  
  
-   Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Он не может содержать `ByRef` параметров.  
  
 Функцию итератор не может содержаться события, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Функции итератора может быть анонимной функции. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Обработка исключений  
 Объект `Yield` инструкцию можно внутри `Try` блока [попробуйте... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Объект `Try` блок, который имеет `Yield` инструкция может иметь `Catch` блокируется и может иметь `Finally` блока.  
  
 Объект `Yield` оператор не может находиться внутри `Catch` блока или `Finally` блока.  
  
 Если `For Each` текст (за пределами функции итератора) вызывает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции итератора. Объект `Catch` блока внутри функции итератора перехватываются только исключения, возникшие внутри функции итератора.  
  
## <a name="technical-implementation"></a>Техническая реализация  
 В следующем коде возвращает `IEnumerable (Of String)` из функции итератора и перебирает элементы `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Вызов `MyIteratorFunction` не выполняет тело функции. Вместо этого вызов возвращает `IEnumerable(Of String)` в переменную `elements`.  
  
 В итерации цикла `For Each` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`. Этот вызов выполняет тело `MyIteratorFunction` до достижения следующего оператора `Yield`. `Yield` Инструкция возвращает выражение, которое определяет не только значение `element` переменной для использования телом цикла, но также <xref:System.Collections.Generic.IEnumerator%601.Current%2A> свойства элементов, которое является `IEnumerable (Of String)`.  
  
 В каждой последующей итерации цикла `For Each` выполнение тела итератора продолжается с места остановки и при достижении оператора `Yield` оно снова останавливается. `For Each` Цикл завершается, когда в конец функции итератора или `Return` или `Exit Function` оператору.  
  
## <a name="example"></a>Пример  
 В следующем примере имеется `Yield` инструкцию, которая находится внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. Каждая итерация [для каждого](../../../visual-basic/language-reference/statements/for-each-next-statement.md) тела оператора в `Main` создает вызов `Power` функции итератора. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 Тип возвращаемого значения метода итератора — <xref:System.Collections.Generic.IEnumerable%601>, является типом интерфейса итератора. При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. Объявление свойства содержит `Iterator` модификатор.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также
- [Операторы](../../../visual-basic/language-reference/statements/index.md)
