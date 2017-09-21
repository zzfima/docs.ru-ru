---
title: "Передача массивов в качестве аргументов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e83c0c119bc1448be76f83416098158c7f5d684
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Передача массивов в качестве аргументов (Руководство по программированию на C#)
Массивы можно передавать в качестве аргументов в параметры метода. Поскольку массивы представляют собой ссылочные типы, метод может изменять значения элементов.  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>Передача одномерных массивов в качестве аргументов  
 Инициализированный одномерный массив можно передать в метод. Например, следующий оператор передает массив в метод печати.  
  
 [!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 В следующем примере кода показана разделяемая реализация метода печати.  
  
 [!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.  
  
 [!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере массив строк инициализируется и передается в качестве аргумента в метод `PrintArray` для строк. Этот метод отображает элементы массива. Далее вызываются методы `ChangeArray` и `ChangeArrayElement`. Это позволяет продемонстрировать, что передача аргумента массива по значению не позволяет предотвратить изменение элементов массива.  
  
### <a name="code"></a>Код  
 [!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>Передача многомерных массивов в качестве аргументов  
 Инициализированный многомерный массив можно передать в метод так же, как и одномерный массив.  
  
 [!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 В следующем коде показано разделяемое объявление метода печати, который принимает в качестве аргумента двухмерный массив.  
  
 [!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.  
  
 [!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере инициализируется двухмерный массив целых чисел, который передается в метод `Print2DArray`. Этот метод отображает элементы массива.  
  
### <a name="code"></a>Код  
 [!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)

