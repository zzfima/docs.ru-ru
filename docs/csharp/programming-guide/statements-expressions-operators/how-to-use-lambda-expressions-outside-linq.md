---
title: "Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
caps.latest.revision: 12
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
ms.openlocfilehash: 29c5d750e428e3ca6efe784cee50ca80bfd63cfd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="cdedd-102">Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="cdedd-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="cdedd-103">Лямбда-выражения не ограничиваются запросами [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdedd-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="cdedd-104">Их можно использовать везде, где ожидается значение делегата, т. е. там, где можно использовать анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="cdedd-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="cdedd-105">В представленном ниже примере показано, как использовать лямбда-выражение в обработчике событий Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cdedd-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="cdedd-106">Обратите внимание на то, что типы входных данных (<xref:System.Object> и <xref:System.Windows.Forms.MouseEventArgs>) выводятся компилятором и не требуют прямого указания параметров лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="cdedd-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdedd-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cdedd-107">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cdedd-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cdedd-108">See Also</span></span>  
 <span data-ttu-id="cdedd-109">[Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="cdedd-109">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="cdedd-110">[Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="cdedd-110">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 [<span data-ttu-id="cdedd-111">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="cdedd-111">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)

