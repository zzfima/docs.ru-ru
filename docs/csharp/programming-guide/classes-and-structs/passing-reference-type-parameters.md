---
title: "Передача параметров ссылочного типа (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2cd862a9179e027ab82631631784203993d0465a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>Передача параметров ссылочного типа (Руководство по программированию в C#)
Переменная [ссылочного типа](../../../csharp/language-reference/keywords/reference-types.md) содержит не сами данные, а ссылку на них. При передаче параметра ссылочного типа по значению можно изменять данные, на которые указывает ссылка, например значение элемента класса. Тем не менее изменить значение самой ссылки нельзя. Это значит, что вы не можете использовать одну и ту же ссылку для выделения памяти для нового класса и его создания вне этого блока. Для этого необходимо передать параметр с использованием ключевого слова [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md). В следующих примерах мы для простоты используем `ref`.  
  
## <a name="passing-reference-types-by-value"></a>Передача ссылочных типов по значению  
 В следующем примере демонстрируется передача параметра ссылочного типа `arr` по значению в метод `Change`. Поскольку этот параметр является ссылкой на `arr`, можно изменять элементы массива. Тем не менее переназначение параметра другому блоку памяти возможно только внутри самого метода и не влияет на исходную переменную `arr`.  
  
 [!code-csharp[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 В предыдущем примере массив `arr` имеет ссылочный тип и передается в метод без параметра `ref`. В таком случае в метод будет передана копия ссылки, которая указывает на `arr`. Как видно из выходных данных, метод может изменять содержимое элемента массива (в данном случае с `1` на `888`). Тем не менее при выделении нового блока памяти с помощью оператора [new](../../../csharp/language-reference/keywords/new.md) внутри метода `Change` переменная `pArray` будет ссылаться на новый массив. Таким образом, любые выполненные после этого изменения не будут отражаться в исходном массиве `arr`, который был создан внутри `Main`. Фактически, в этом примере создается два массива: один внутри `Main`, а другой — в методе `Change`.  
  
## <a name="passing-reference-types-by-reference"></a>Передача ссылочных типов по ссылке  
 Следующий пример аналогичен предыдущему, однако в нем в заголовок и вызов метода добавляется ключевое слово `ref`. Любые изменения, выполняемые в методе, влияют на исходную переменную в вызывающей программе.  
  
 [!code-csharp[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 Все изменения, выполняемые внутри метода, влияют на исходный массив в `Main`. Фактически, происходит перемещение исходного массива с помощью оператора `new`. Таким образом, после вызова метода `Change` любые ссылки на `arr` будут указывать на массив из пяти элементов, который создается в методе `Change`.  
  
## <a name="swapping-two-strings"></a>Перестановка двух строк  
 Перестановка строк представляет собой наглядный пример передачи параметров ссылочного типа по ссылке. В этом примере две строки (`str1` и `str2`) инициализируются в `Main`, а затем передаются в метод `SwapStrings` в качестве параметров, измененных по ключевому слову `ref`. Перестановка двух строк выполняется как в этом методе, так и в `Main`.  
  
 [!code-csharp[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 В этом примере параметры должны передаваться по ссылке, чтобы обеспечить изменение переменных в вызывающей программе. Если удалить ключевое слово `ref` из заголовка и вызова метода, в вызывающей программе не будут выполнены никакие изменения.  
  
 Дополнительные сведения о строках см. в [этом разделе](../../../csharp/language-reference/keywords/string.md).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
 [ref](../../../csharp/language-reference/keywords/ref.md)  
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)
