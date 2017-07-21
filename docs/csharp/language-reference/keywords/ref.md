---
title: "ref (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 353abf8a0c852acbbb2949f9640c1465dec8593b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="ref-c-reference"></a>ref (Справочник по C#)
Ключевое слово `ref` используется для передачи аргумента по ссылке, а не по значению. Эффект передачи по ссылке в том, что все изменения вызываемого метода отражаются на значении переменной аргумента, используемой в вызове метода. Например если вызывающий объект передает выражение локальной переменной или выражение доступа к элементу массива и вызванный метод заменяет объект, на который ссылается параметр ref, то локальная переменная или элемент массива взывающего объекта теперь ссылаться на новый объект.  
  
> [!NOTE]
>  Не следует путать понятие передачи по ссылке с понятием ссылочных типов. Эти два понятия не совпадают. Параметр метода может быть изменен с помощью `ref` независимо от того, принадлежит ли он к типу значения или ссылочному типу. При передаче по ссылке упаковка-преобразование типа значения не производится.  
  
 Для использования параметра `ref` и при определении метода, и при вызове метода следует явно использовать ключевое слово `ref`, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsMethodParams#6](../../../samples/snippets/csharp/language-reference/keywords/ref/ref_1.cs)]  
  
 Аргумент, передаваемый в параметр `ref`, перед передачей должен быть инициализирован. В этом заключается отличие от параметров `out`, аргументы которых не требуют явной инициализации перед передачей. Дополнительные сведения см. в разделе [out](../../../csharp/language-reference/keywords/out.md).  
  
 Члены класса не могут иметь сигнатуры, отличие которых заключается только в `ref` и `out`. Если единственное различие между двумя членами типа состоит в том, что один из них имеет параметр `ref`, а второй имеет параметр `out`, возникает ошибка компилятора. Например, следующий код не будет компилироваться.  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../samples/snippets/csharp/language-reference/keywords/ref/ref_2.cs)]  
  
 Однако перегрузка может быть выполнена, если один метод принимает параметр `ref` или `out`, а другой принимает параметр по значению, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsMethodParams#7](../../../samples/snippets/csharp/language-reference/keywords/ref/ref_3.cs)]  
  
 В других ситуациях, требующих соответствия сигнатур, таких как скрытие или переопределение, `ref` и `out` являются частью сигнатуры и не соответствуют друг другу.  
  
 Свойства не являются переменными. Они являются методами и не могут быть переданы в параметр `ref`.  
  
 Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.  
  
-   Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  
  
## <a name="example"></a>Пример  
 В предыдущих примерах показано, что происходит при передаче типов значений по ссылке. Можно также использовать ключевое слово `ref` для передачи ссылочных типов. Передача ссылочного типа по ссылке позволяет вызываемому методу изменять объект, на который указывает ссылочный параметр. Место хранения объекта передается методу в качестве значения ссылочного параметра. Если изменить место хранения параметра (с указанием на новый объект), необходимо изменить место хранения, на который ссылается вызывающий объект. В следующем примере экземпляр ссылочного типа передается как параметр `ref`. Дополнительные сведения о передаче ссылочных типов по значению и по ссылке см. в разделе [Передача параметров ссылочного типа](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).  
  
 [!code-cs[csrefKeywordsMethodParams#8](../../../samples/snippets/csharp/language-reference/keywords/ref/ref_4.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
