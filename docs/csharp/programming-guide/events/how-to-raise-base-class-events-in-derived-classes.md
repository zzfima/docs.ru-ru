---
title: "Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 548409d3f632213f3ff1de0a27a70b9f42b18332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#)
В следующем простом примере показан стандартный способ объявления событий в базовом классе, позволяющий вызывать их из производных классов. Этот шаблон активно применяется в классах Windows Forms в библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 При создании класса, который можно использовать в качестве базового для других классов, следует учитывать тот факт, что события представляют собой особый тип делегатов, который может вызываться только в том классе, который их объявил. Производные классы не могут создавать события, объявленные в базовом классе, напрямую. Несмотря на то, что в некоторых обстоятельствах вам может потребоваться событие, вызываемое только базовым классом, в большинстве случаев рекомендуется разрешать производному классу вызывать события базового класса. Для этого следует создать в базовом классе защищенный метод, предоставляющий оболочку для события. Вызывая или перезаписывая вызывающий метод, производные классы могут вызывать событие косвенно.  
  
> [!NOTE]
>  Не объявляйте виртуальные события в базовом классе и не переопределяйте их в производном классе. Компилятор c# не обрабатывает их корректно, поэтому сложно сказать, будет ли подписчик производного события на самом деле подписываться на событие базового класса.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [События](../../../csharp/programming-guide/events/index.md)  
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Создание обработчиков событий в Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx)
