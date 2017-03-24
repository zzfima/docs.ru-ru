---
title: "Оператор yield (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a>Оператор Yield (Visual Basic)
Отправляет следующий элемент коллекции для `For Each...Next` инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, которое может быть неявно преобразован в тип функции итератора или `Get` метод доступа, который содержит `Yield` инструкции.|  
  
## <a name="remarks"></a>Примечания  
 `Yield` Инструкция возвращает один элемент коллекции одновременно. `Yield` Инструкция включена в функции итератора или `Get` доступа, который будет выполнять пользовательские итерации по коллекции.  
  
 Использование функции итератора с помощью [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или запрос LINQ. Каждая итерация `For Each` цикл вызывает функции итератора. Когда `Yield` достижении оператора в функции итератора `expression` возвращается и сохраняется текущее расположение в коде. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Должно существовать неявное преобразование из типа `expression` в `Yield` инструкции в возвращаемый тип итератора.  
  
 Можно использовать `Exit Function` или `Return` инструкции для завершения итерации.  
  
 «Доход» не является зарезервированным словом и имеет специальное значение только в том случае, если он используется в `Iterator` функции или `Get` доступа.  
  
 Дополнительные сведения о функции итератора и `Get` методы доступа, в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="iterator-functions-and-get-accessors"></a>Функции итератора и методы доступа Get  
 Объявление функции итератора или `Get` доступа должен соответствовать следующим требованиям:  
  
-   Он должен содержать [итератор](../../../visual-basic/language-reference/modifiers/iterator.md) модификатор.  
  
-   Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
-   Он не может содержать `ByRef` параметров.  
  
 Функция итератор не может содержаться событие, конструктор экземпляра, статический конструктор или деструктор статический.  
  
 Функции итератора может быть анонимной функции. Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="exception-handling"></a>Обработка исключений  
 Объект `Yield` инструкция может находиться внутри `Try` блока [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Объект `Try` блок, который имеет `Yield` инструкция может иметь `Catch` блокируется и может иметь `Finally` блок.  
  
 Объект `Yield` оператор не может находиться внутри `Catch` блока или `Finally` блока.  
  
 Если `For Each` текст (за пределами функции итератора) вызывает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции итератора. A `Catch` блок внутри функции итератора перехватывает только исключения, которые возникают внутри функции итератора.  
  
## <a name="technical-implementation"></a>Техническая реализация  
 Следующий код возвращает `IEnumerable (Of String)` из функции итератора и перебирает элементы `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Вызов `MyIteratorFunction` тело функции не выполняется. Вместо этого вызов возвращает `IEnumerable(Of String)` в переменную `elements`.  
  
 В итерации `For Each` цикл, <xref:System.Collections.IEnumerator.MoveNext%2A>метод вызывается для `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A> Этот вызов выполняет тело `MyIteratorFunction` до достижения следующего оператора `Yield`. `Yield` Инструкция возвращает выражение, определяющее значение не только `element` переменной для использования телом цикла, но также <xref:System.Collections.Generic.IEnumerator%601.Current%2A>Свойства элементов, который является `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A>  
  
 В каждой последующей итерации цикла `For Each` выполнение тела итератора продолжается с места остановки и при достижении оператора `Yield` оно снова останавливается. `For Each` Цикл завершается, когда конец функции итератора или `Return` или `Exit Function` к оператору.  
  
## <a name="example"></a>Пример  
 В следующем примере `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла. Каждая итерация [для каждого](../../../visual-basic/language-reference/statements/for-each-next-statement.md) тела оператора в `Main` создает вызов `Power` функции итератора. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 Возвращаемый тип метода итератора — <xref:System.Collections.Generic.IEnumerable%601>, тип интерфейса итератора.</xref:System.Collections.Generic.IEnumerable%601> При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.  
  
 [!code-vb[VbVbalrStatements&#98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. Объявление включает в себя `Iterator` модификатор.  
  
 [!code-vb[VbVbalrStatements&#99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 Дополнительные примеры см. в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)   
 [Операторы](../../../visual-basic/language-reference/statements/index.md)
