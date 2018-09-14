---
title: Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: eb9fea64b8aeb96a880b7e177673c1316b7aa4c1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261541"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
Лямбда-выражения не ограничиваются запросами [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Их можно использовать везде, где ожидается значение делегата, т. е. там, где можно использовать анонимный метод. В представленном ниже примере показано, как использовать лямбда-выражение в обработчике событий Windows Forms. Обратите внимание на то, что типы входных данных (<xref:System.Object> и <xref:System.Windows.Forms.MouseEventArgs>) выводятся компилятором и не требуют прямого указания параметров лямбда-выражений.  
  
## <a name="example"></a>Пример  
  
```csharp  
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

- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [Синтаксис LINQ](../../../csharp/programming-guide/concepts/linq/index.md)
