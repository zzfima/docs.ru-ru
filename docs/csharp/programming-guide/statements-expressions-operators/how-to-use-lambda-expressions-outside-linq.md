---
title: Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: 6ba6c6f50b4d2f717de4325b5cd21434066b2899
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43389188"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="4e77e-102">Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4e77e-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="4e77e-103">Лямбда-выражения не ограничиваются запросами [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e77e-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="4e77e-104">Их можно использовать везде, где ожидается значение делегата, т. е. там, где можно использовать анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="4e77e-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="4e77e-105">В представленном ниже примере показано, как использовать лямбда-выражение в обработчике событий Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4e77e-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="4e77e-106">Обратите внимание на то, что типы входных данных (<xref:System.Object> и <xref:System.Windows.Forms.MouseEventArgs>) выводятся компилятором и не требуют прямого указания параметров лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="4e77e-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e77e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="4e77e-107">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e77e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4e77e-108">See Also</span></span>  
 [<span data-ttu-id="4e77e-109">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="4e77e-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="4e77e-110">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="4e77e-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="4e77e-111">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="4e77e-111">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
