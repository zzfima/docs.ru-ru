---
title: Как выполнить Руководство по программированию на C#. Использование лямбда-выражений вне LINQ
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: d4dc0375552ef1fe00f629c22b5296399b4cc99d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243937"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование лямбда-выражений вне LINQ
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
