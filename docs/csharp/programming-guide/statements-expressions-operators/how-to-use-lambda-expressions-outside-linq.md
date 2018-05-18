---
title: Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: a7b7d25adab7ce1fc777b3bdbe581666ab952413
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
Лямбда-выражения не ограничиваются запросами [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Их можно использовать везде, где ожидается значение делегата, т. е. там, где можно использовать анонимный метод. В представленном ниже примере показано, как использовать лямбда-выражение в обработчике событий Windows Forms. Обратите внимание на то, что типы входных данных (<xref:System.Object> и <xref:System.Windows.Forms.MouseEventArgs>) выводятся компилятором и не требуют прямого указания параметров лямбда-выражений.  
  
## <a name="example"></a>Пример  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
